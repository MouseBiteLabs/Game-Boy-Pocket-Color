# Technical Design Document

This write-up serves as a technical explainer document for the MGBC project. I will not be covering the 5 V power supply board in detail in this explainer; this document is intended for the main MGBC-MBL-01 PCB only. Furthermore, I will not be explaining *every* circuit element in this document, especially the straightforward connections present on the original GBC schematic (i.e. cart connector, link port, etc). The majority of coverage here will be on the new features I have added to the project.

## Power Supply

![image](https://user-images.githubusercontent.com/97127539/232262379-b7438268-40c1-4e26-ada2-07371bb3e060.png)

(I know the symbols for the fuses and filters are incorrect. I needed an 0603 package for the board and was too lazy to assign the parts the correct symbols. But I guess technically… they are all resistors in some form.)

- The MGBC is compatible with many other aftermarket DC/DC converter boards (check the compatibility list in the main README file). However, one important distinction exists on the MGBC. Pin 1 of U5 is connected to the output of the power switch - as the OEM and many other DC/DC converter mods do - but also, pin 2 is directly and always connected to the power input (battery or DC jack). Pin 2 on U5 is normally unused, but my converter board (the <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Pocket Mouse Power Board</a>) uses pin 1 to control the enable pin of the boost converter, and takes main power in from pin 2 instead. As of this writing, only my board utilizes this previously-unused pin to achieve this. The end effect is that the system current does not pass through the power switch, which can be dirty or oxidized and introduce unwanted voltage drops at higher currents, ultimately increasing reliability of the system. <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board/tree/main/Technical">Check the technical write-up of the Pocket Mouse Power Board for more information.</a>
- F1 provides protection to the batteries in the event of any overcurrent condition. F2 provides protection to the DC jack in the event of an overcurrent condition. D2 provides reverse polarity protection in the event the batteries are placed in backwards (something kind of difficult to do, actually).
- Pins 2 and 3 on the DC jack are normally closed when the AC adapter is *not* plugged in, and open when it is plugged in. This ensures the batteries and AC adapter cannot power the Game Boy simultaneously, and prevents accidental backfeeding into the opposing power source.
- R1 discharges components connected to the output of the power switch when the power switch is turned off, ensuring quick discharge and reducing the chance of strange operation during a slower power down.
- U4 is a simple linear regulator for generating the 3.3 V supply necessary for the RAM and the CPU core. I considered using a SMPS instead, but the current requirements are so low, it seemed slightly overkill.
- The filters (EM6, 7, 8, and 10) are likely fine to exclude, but it doesn't hurt to include them just in case some weird high frequency components have the potential to screw something up down the line. I don't really have the capability (or desire) to properly test what effects removing them may have, but I suspect they're mostly for FCC compliance.
- EM7 *must* be completely removed if you want to use a USB-C port in place of the DC jack for charging a LiPo battery. The "DC" test point can be used for the USB-C input to the LiPo charger. The "BT+" test point can be used as the output of the charger, which should be managing the output of the LiPo battery. *You should not connect AAA batteries if you are LiPo modding your MGBC - depopulate the battery contacts!*

## Power LED Indicator

![image](https://user-images.githubusercontent.com/97127539/232262578-89d663ab-6faa-4ef9-830f-36856ece43e9.png)

- SW is the voltage coming from the power source (batteries, DC jack). The BATT test pad in the schematic is for connecting to the OSD display for battery level indication. Note that if you are using a LiPo, the OSD will not accurately read the battery voltage level. (I couldn't be bothered to include a scaling circuit to address this!)
- R4 and C3 is a simple RC filter to keep the battery level reading steady during transient loads, such as when the audio is loud.
- U7, R2, R4, R5, and R8 set up a non-inverting Schmitt trigger. When the battery voltage is above ~2.2 V, the output of U7 (pin 4) is pulled up by R11 to 5 V. This drives the base of Q2 to short R10, reducing the resistance in series with LED1. When the battery value drops below ~2.2 V, pin 4 is pulled to GND. This turns off Q2, connecting R10 in series with and dimming LED1.

## FFC Connector

For this build, as mentioned, I'm using the GBC Q5 XL IPS Backlight with OSD kit. It comes with a separate circuit board to properly drive the IPS screen (which I’m henceforth calling the “Q5 board”). In order to determine which pins were necessary for the Q5 board, I looked at the cable connected to the board and noted which traces actually go somewhere. The pins in red are unused, the ones in blue are used. The pin names are from the GBC schematic.

![image](https://user-images.githubusercontent.com/97127539/229975715-6d78bbc5-13a3-4177-994b-4fde97fc7a21.png)

## Audio Amplifier

The new audio circuit on the MGBC is powered by the LM4853, the same as my DMGC project. This TI chip is perfectly suited for the Game Boy - it has stereo inputs and headphone outputs, and mono speaker output. Makes it quite easy to implement without extra circuitry shenanigans.

![image](https://user-images.githubusercontent.com/97127539/229975808-5cc1704a-90c0-4aee-af4d-3559ff87c255.png)

- C18/C19 are DC blocking capacitors and RA1A/RA1B are current limiting resistors, so when the volume is turned all the way down, the S01 and S02 pins aren’t overloaded.
- C52/C53 are DC blocking capacitors so only the AC audio signal passes to the amplifier.
- The ratio of R30/R31 and R32/R33 set the amplification of the audio amp - increase R30 and R32 to decrease the output volume.
  - The audio gain has quite a large effect on the power draw of the system when using the speaker. I did not do any tests with an audio gain greater than ~0.5. A sufficiently larger gain than this will drain batteries faster if the volume is turned up.
- The shutdown pin should be tied to GND to allow the amp to work. The output on the headphones will sound really quiet and the speaker won't work if the chip is shutdown.
- The headphone detect pin (HP_SWITCH) is connected to GND when the headphone jack is empty, and is pulled up to 5 V via R36 when headphones are inserted. This switches the output on the audio amplifier between the speakers and headphones. C51 is for debouncing the headphone detection.
- C26/C27 are DC blocking capacitors so only the AC audio signal passes to the headphones.
- The speaker output shouldn't need a DC blocking capacitor, as the LM4853 outputs to the speaker as a bridge tied load (BTL). However, I found that if a DC blocking capacitor is not included, a strange issue is possible in specific situations. There’s a very brief moment when plugging the headphones in where the right output channel is shorted to ground (ring and sleeve are connected inside the jack). When this happens, the right output DC blocking cap is connected to GND, and causes a large surge of current from the power supply to charge it up. In my testing, this sometimes would cause a brownout, causing the power supply to shut off. Therefore, I have included C8 for DC blocking. 
- Similarly, R22 and R23 are included to pull down the negative sides of the DC blocking capacitors C26 and C27 when headphones are not connected – without them, the outputs would be floating. This will prevent inrush current during headphone insertion, which I have seen cause issues with the LM4853 in the past.

## CPU Reset

I’ve replaced the original PST9135N with a TPS3840DL35. These chips pull the /RESET pin on the CPU low when the voltage supply drops below 3.5 V (/RESET set to low turns off the CPU). The TPS3840DL35 does the same thing. The reason this chip is included is to hold the CPU off while powering down so no random instructions are made while the game is turning off.

R3 and C17 introduces a time delay on the /RESET pin during start-up, to allow the rest of the power supplies to stabilize before letting the CPU operate. This is called a "power-on reset" circuit, and I used values that the original GBC schematic used. (The DMG, GBC, and GBA all use the same odd 18 ms time constant!)

![image](https://user-images.githubusercontent.com/97127539/229975938-e13f1dd8-ba86-43c4-9b4a-31103082808e.png)

## Navigation Switch

This takes place where the contrast wheel used to be. On the Q5 board, there are two capacitive touch sensors - one for changing brightness, one for changing the color palette. Instead of using the touch sensors in the MGBC, the navigation switch will toggle these inputs by connecting a series capacitance to ground to simulate a touch. This also has the benefit of not having to modify the driver board in any way, and instead just requiring soldered wires to the board where capacitive sensors were connected.

![image](https://user-images.githubusercontent.com/97127539/229975981-64d72321-9d51-4f81-8900-453c6fdfeb54.png)

Rocking up on the dial will toggle the brightness setting, rocking it down will toggle the color palette setting. Rocking up and holding it will toggle the battery level display on the screen, and rocking it down and holding it will toggle the pixel grid. Pushing in on the switch grounds the /RESET line on the CPU to act as a reset button, if the designated solder pads are bridged.

## OSD Pads

There are six test points at the top of the MGBC for short wires to connect to the Q5 board. The Q5 board includes pads for the select, B, and A buttons for navigation in the OSD. And as previously mentioned - there's a battery pad, which is for measuring the battery life on the OSD, and two pads for brightness control and color palette swapping.

![image](https://user-images.githubusercontent.com/97127539/229976001-32295e79-65a5-4af5-8109-cc9323a7e055.png)

# Resources

- <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Pocket Mouse Power Board repo</a>
-	<a href="https://console5.com/techwiki/images/e/e6/Nintendo_GBC_Schematic.png">GBC schematic</a>
-	<a href="https://www.ti.com/lit/ds/symlink/lm4853.pdf?ts=1656384256966&ref_url=https%253A%252F%252Fwww.google.com%252F">LM4853 datasheet</a>

# License
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>. You are able to copy and redistribute the material in any medium or format, as well as remix, transform, or build upon the material for any purpose (even commercial) - but you **must** give appropriate credit, provide a link to the license, and indicate if any changes were made.

©MouseBiteLabs 2023
