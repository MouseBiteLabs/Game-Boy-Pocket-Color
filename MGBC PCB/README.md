# MGBC-MBL-01

Version 1.4:
![image](https://user-images.githubusercontent.com/97127539/235451668-f54230a5-8303-46f6-8453-fe5080dfdbc3.png)
Version 1.4S:
![image](https://user-images.githubusercontent.com/97127539/235395330-059e9334-d244-4df9-a113-023d8dffeb3a.png)

This is the main circuit board in the MGBC build. This README will provide instructions for how to customize the build to your liking, as well as attempt to clear up any questions you may have about the build process.

## Board Characteristics

The zipped folder contains all the gerber files for this board, if you wish to order it from a board manufacturer yourself. Version 1.x refers to the PCB that is one solid color with little-to-no visible silkscreen on the front after assembly; Version 1.xS refers to the PCB that has the bottom half filled with slikscreen, to make it look like OEM Pocket boards.

-	Layers: 2
-	Thickness: 1 mm
-	Surface Finish: ENIG (or HASL, which is only acceptable if you are installing tactile buttons)
-   **NOTE: When ordering PCBs, add this note to the order: "The file milling.gbr contains outlines for plated slots. Please add plated slots on the PCB according to this layer."**

I sell this board on Etsy, so you don't have to buy multiples from board fabricators.

You can alternatively use the zipped folder at any board fabricator you like. You may also buy the board from PCBWay using this link (disclosure: I receive 10% of the sale value to go towards future PCB orders):

[link]

## Customization Options

This section will explain all of the different customization options available on this board while you assemble.

### Adjusting Volume Range

You can adjust the maximum volume coming out of the speakers and headphones by modifying R30 and R32 values. Increase R30 and R32 to decrease the maximum volume; decrease R30 and R32 to increase the maximum volume. Choose the same values for both of these resistors, otherwise you'll have lopsided audio channels. After some trial and error, here's my approximations of some different values of resistors:

- Choosing 100 kΩ for a gain of ~0.18 will yield about the same volume as a stock GBC.
- Using 47 kΩ seemed to hit a sweet spot for my tastes for a gain of ~0.38 - not too loud, not too quiet. If I'm playing at max volume, you can hear it between floors in my house, so being any louder is likely not necessary.
- The lowest value I tried out was 33 kΩ, but this was considerably loud. It also began to have an actual impact in the battery voltage. I suspect values lower than about 20 kΩ will greatly reduce battery life.

![image](https://user-images.githubusercontent.com/97127539/235404925-43ea18f5-89dc-4755-ad6b-a9f0dff53e54.png)

### Enabling Reset Button Functionality

Bridge the pads labelled "RST" with solder to turn the navigation switch into a reset button whenever you push it in. It's not particularly easy to push the button in, so accidental resets shouldn't be a concern. But if you find yourself accidentally resetting the system, you can remove the solder from the pads to disable it.

![image](https://user-images.githubusercontent.com/97127539/235404437-c3ce6e13-eaac-4a32-95bc-a18a6ef214d2.png)

### Power LED Brightness

Increase the value of R1 to decrease the brightness of the power LED during normal battery levels. Increase the value of R2 to decrease the brightness of the power LED during low battery levels. It is suggested to try changing resistances in ~10 kΩ increments.

![image](https://user-images.githubusercontent.com/97127539/235404599-46a0dd64-a8e6-485e-ace7-022baa46350d.png)

### Tactile Switches

If you want clicky buttons, like the GBA SP has, then you can install tactile switches onto the button contacts. These are listed as B1-B8 on the BOM. There are three levels of clickiness to choose from, depending on the part number you select - SKRRAAE010 is the "least clicky" with 1 N operating force, SKRRABE010 has 1.6 N of operating force, and SKRRACE010 is the "most clicky" with 2 N of operating force. Note when installing the switches to make sure the little "wings" are oriented correctly as indicated on the board!

![image](https://user-images.githubusercontent.com/97127539/235406753-a694bea7-ffcf-4bec-903d-00f39ec4b2d9.png)

### LiPo Support

Are you using the Game Boy Pocket Power regulator for U5 for LiPo support? If so, solder wires or headers from the DC and BT+ holes into the GBPP, thread the wires from the battery through the hole in the board to the GBPP connections, and remember to **REMOVE EM7**. You'll also need a USB-C adapter PCB to go in place of DC jack.

![image](https://user-images.githubusercontent.com/97127539/235404692-459eaaf9-e352-4ebe-bb32-7ae6a3937a24.png)

## Assembly References

Here are a few images that should help clarify the build process, as well as provide some brief technical explanations to guide you in troubleshooting any errors you might have.

### Part Placement

Some of the parts are a bit cramped, and it can be a bit difficult to decipher which part is which. Hopefully this image helps you clarify.

![image](https://user-images.githubusercontent.com/97127539/235396199-3f610782-8782-44d2-b0a4-8c2cef4e248b.png)

### CPU Pin Functions

This is a bit of a mess, but depending on the problem you're encountering, it could be worth reflowing the pins on the CPU that correspond to the aspect you're having problems with.
- For miscolored screens, reflow the top display pins.
- For *glitchy* screens, or frozen/all-white screens, reflow the SRAM pins.
- If you're missing button inputs, reflow the bottom left corner button pins.
- If you have games that don't start up properly and hang at the Nintendo logo during start-up, display a glitchy Nintendo logo, or randomly freeze during gameplay, reflow the cartridge pins. (And clean your cartridge connector)
- Three link port pins are on the bottom right, but there is one lone one at the top.
- In general, reflowing the clock and power pins (colored red, pink, and black) can solve problems as well.

![image](https://user-images.githubusercontent.com/97127539/235403819-e2aaaf66-5f18-482f-b601-76027f41c5d1.png)

## Bill of Materials

This should be for reference only. This can be found in the main folder in Excel format. There is also a link in the main folder for a saved Mouser cart with all these parts.

| Reference Designators                     | Qty | Value/Part Number | Package     | Description        | Comment                                                                                                           | Source                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------- | --- | ----------------- | ----------- | ------------------ | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| B1-B8                                     | 8   | SKRRABE010        |             | Tactile switch     | Optional, can be omitted if you don't want clicky SP-style buttons (SKRRAA is less clicky, SKRRAC is more clicky) | [https://www.mouser.com/ProductDetail/688-SKRRAB](https://www.mouser.com/ProductDetail/688-SKRRAB)                                                                                                                                                                                                                           |
| BT+, BT-                                  | 2   |                   |             | Battery terminals  | Can be salvaged from MGB instead                                                                                  | [https://retrogamerepairshop.com/collections/gbp-power/products/gbp-game-boy-pocket-high-quality-replacement-battery-contact-terminals?variant=37893131305132](https://retrogamerepairshop.com/collections/gbp-power/products/gbp-game-boy-pocket-high-quality-replacement-battery-contact-terminals?variant=37893131305132) |
| C1                                        | 1   | 18pF              | 0603        | Capacitor (MLCC)   | Should be X5R (or better); at least 1% tolerance; at least 16V                                                    | [https://www.mouser.com/ProductDetail/YAGEO/CC0603FRNPO9BN180?qs=vTakOoo5QyL0KzYUzHPSUw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/CC0603FRNPO9BN180?qs=vTakOoo5QyL0KzYUzHPSUw%3D%3D)                                                                                                                                 |
| C12, C24, C43, C52, C53                   | 5   | 100nF             | 0603        | Capacitor (MLCC)   | Should be X5R (or better), at least 16V                                                                           | [https://www.mouser.com/ProductDetail/KEMET/C0603C104M3RACTU?qs=7q2aiX3Gdlh4qBRaMcnohQ%3D%3D](https://www.mouser.com/ProductDetail/KEMET/C0603C104M3RACTU?qs=7q2aiX3Gdlh4qBRaMcnohQ%3D%3D)                                                                                                                                   |
| C2, C15, C20                              | 3   | 27pF              | 0603        | Capacitor (MLCC)   | Should be X5R (or better); at least 1% tolerance; at least 16V                                                    | [https://www.mouser.com/ProductDetail/603-C0603FRNPO9BN270](https://www.mouser.com/ProductDetail/603-C0603FRNPO9BN270)                                                                                                                                                                                                       |
| C3, C11, C16-C19, C39, C40, C48, C49, C51 | 11  | 1uF               | 0603        | Capacitor (MLCC)   | Should be X5R (or better), at least 16V                                                                           | [https://www.mouser.com/ProductDetail/KEMET/C0603C105K3PACTU?qs=STjISULpmtalQKXy67%252B4Cg%3D%3D](https://www.mouser.com/ProductDetail/KEMET/C0603C105K3PACTU?qs=STjISULpmtalQKXy67%252B4Cg%3D%3D)                                                                                                                           |
| C4                                        | 1   | 22pF              | 0603        | Capacitor (MLCC)   |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/CC0603JRNPO9BN220?qs=vTakOoo5QyIVMYOUTI%2F4zA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/CC0603JRNPO9BN220?qs=vTakOoo5QyIVMYOUTI%2F4zA%3D%3D)                                                                                                                             |
| C47                                       | 1   | 150pF             | 0603        | Capacitor (MLCC)   |                                                                                                                   | [https://www.mouser.com/ProductDetail/KEMET/C0603C151J5GACTU?qs=V6nSPVTm7vxbAvL0weNH%252BQ%3D%3D](https://www.mouser.com/ProductDetail/KEMET/C0603C151J5GACTU?qs=V6nSPVTm7vxbAvL0weNH%252BQ%3D%3D)                                                                                                                           |
| C5-C7, C13, C14                           | 5   | 100pF             | 0603        | Capacitor (MLCC)   |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/CC0603JPNPO9BN101?qs=7s%252B3O6pAiyAo%2FUxNqKltRA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/CC0603JPNPO9BN101?qs=7s%252B3O6pAiyAo%2FUxNqKltRA%3D%3D)                                                                                                                     |
| C8, C26, C27                              | 3   | 100uF             | 1206        | Capacitor (Tant)   | Experiment with different types if you want                                                                       | [https://www.mouser.com/ProductDetail/KYOCERA-AVX/TLJA107M006R0800?qs=o28%2FEEzBmj1LB376wnSl1g%3D%3D](https://www.mouser.com/ProductDetail/KYOCERA-AVX/TLJA107M006R0800?qs=o28%2FEEzBmj1LB376wnSl1g%3D%3D)                                                                                                                   |
| C9, C10, C29, C33, C41, C45               | 6   | 10nF              | 0603        | Capacitor (MLCC)   | Should be X5R (or better), at least 16V                                                                           | [https://www.mouser.com/ProductDetail/KEMET/C0603C103J5RACTU?qs=BimOss5pjlFJEfKhlb7g1g%3D%3D](https://www.mouser.com/ProductDetail/KEMET/C0603C103J5RACTU?qs=BimOss5pjlFJEfKhlb7g1g%3D%3D)                                                                                                                                   |
| D1                                        | 1   | PMEG2010AEH       | SOD-123     | Schottky diode     | Most schottky diodes should be suitable (at least 1A, 16V)                                                        | [https://www.mouser.com/ProductDetail/?qs=LOCUfHb8d9u7lcjEnyhX1g%3D%3D](https://www.mouser.com/ProductDetail/?qs=LOCUfHb8d9u7lcjEnyhX1g%3D%3D)                                                                                                                                                                               |
| EM10                                      | 1   | 744235601         | 1812        | Common mode filter | Can be salvaged from CGB instead                                                                                  | [https://www.mouser.com/ProductDetail/Wurth-Elektronik/744235601?qs=BXmE%252BJ0Y7xYO4MPd53j2NQ%3D%3D](https://www.mouser.com/ProductDetail/Wurth-Elektronik/744235601?qs=BXmE%252BJ0Y7xYO4MPd53j2NQ%3D%3D)                                                                                                                   |
| EM2-EM4, EM9                              | 4   | BLM18BD102SN1D    | 0603        | Filter             |                                                                                                                   | [https://www.mouser.com/ProductDetail/Murata-Electronics/BLM18BD102SN1D?qs=h3IWXJJGQQWi4eZyJq6ScQ%3D%3D](https://www.mouser.com/ProductDetail/Murata-Electronics/BLM18BD102SN1D?qs=h3IWXJJGQQWi4eZyJq6ScQ%3D%3D)                                                                                                             |
| EM6-EM8                                   | 3   | Z0805C221BPWZT    | 0805        | Filter             | Replacement: FBMH2012HM221-T                                                                                      | https://www.mouser.com/ProductDetail/KEMET/Z0805C221BPWZT?qs=W0XMKc1ssG4b8%2FEBVn2KJA%3D%3D                                                                                                                                                                                                                                  |
| F1, F2                                    | 2   | 1A                | 0603        | Fuse               |                                                                                                                   | [https://www.mouser.com/ProductDetail/Vishay-Beyschlag/MFU0603FF01000P100?qs=oI046glRurtlP8n%252B3l7CPg%3D%3D](https://www.mouser.com/ProductDetail/Vishay-Beyschlag/MFU0603FF01000P100?qs=oI046glRurtlP8n%252B3l7CPg%3D%3D)                                                                                                 |
| FB1                                       | 1   | BLA31AG601SN4D    | 1206        | Ferrite Bead       |                                                                                                                   | [https://www.mouser.com/ProductDetail/Murata-Electronics/BLA31AG601SN4D?qs=2ahBf5rJw09FDcUVkQibEg%3D%3D](https://www.mouser.com/ProductDetail/Murata-Electronics/BLA31AG601SN4D?qs=2ahBf5rJw09FDcUVkQibEg%3D%3D)                                                                                                             |
| LED1                                      | 1   | 151033RS03000     | 3mm         | Red LED            |                                                                                                                   | [https://www.mouser.com/ProductDetail/Wurth-Elektronik/151033RS03000?qs=LlUlMxKIyB1%252BAw6bWFN43w%3D%3D](https://www.mouser.com/ProductDetail/Wurth-Elektronik/151033RS03000?qs=LlUlMxKIyB1%252BAw6bWFN43w%3D%3D)                                                                                                           |
| P1                                        | 1   |                   |             | Cart connector     |                                                                                                                   | Salvaged (MGB/CGB)                                                                                                                                                                                                                                                                                                           |
| P2                                        | 1   | 62684-502100AHLF  |             | LCD connector      | Can be salvaged from CGB instead                                                                                  | [https://www.mouser.com/ProductDetail/?qs=HL%252BYNjdyZ0vzwc9E0QYY2g%3D%3D](https://www.mouser.com/ProductDetail/?qs=HL%252BYNjdyZ0vzwc9E0QYY2g%3D%3D)                                                                                                                                                                       |
| P3                                        | 1   |                   |             | Link port          | Can be salvaged from MGB/CGB instead                                                                              | [https://retrogamerepairshop.com/collections/gbp-accessories/products/link-cable-replacement-port-for-gbc-gbp-gbl?variant=41808976183468](https://retrogamerepairshop.com/collections/gbp-accessories/products/link-cable-replacement-port-for-gbc-gbp-gbl?variant=41808976183468)                                           |
| P4                                        | 1   |                   |             | DC Jack            | Can be salvaged from MGB/CGB instead                                                                              | [https://www.aliexpress.us/item/2255800460672253.html?spm=a2g0o.order_list.order_list_main.23.c0c31802sdJmTz&gatewayAdapt=glo2usa&_randl_shipto=US](https://www.aliexpress.us/item/2255800460672253.html?spm=a2g0o.order_list.order_list_main.23.c0c31802sdJmTz&gatewayAdapt=glo2usa&_randl_shipto=US)                       |
| P5                                        | 1   |                   |             | Headphone jack     |                                                                                                                   | Salvaged (MGB/CGB)                                                                                                                                                                                                                                                                                                           |
| Q2                                        | 1   | MMBT3904          | SOT23       | NPN BJT            |                                                                                                                   | [https://www.mouser.com/ProductDetail/Nexperia/MMBT3904VL?qs=cnAQGvEIVkKbCwIpHJoHxQ%3D%3D](https://www.mouser.com/ProductDetail/Nexperia/MMBT3904VL?qs=cnAQGvEIVkKbCwIpHJoHxQ%3D%3D)                                                                                                                                         |
| R1, R22, R23                              | 3   | 1k                | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071KL?qs=VU8sRB4EgwApHsk4rF%2F3zg%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071KL?qs=VU8sRB4EgwApHsk4rF%2F3zg%3D%3D)                                                                                                                                   |
| R2, R25                                   | 2   | 1.5M              | 0603        | Resistor           | Recommended at least 1% tolerance                                                                                 | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071M5L?qs=VU8sRB4EgwAP38Z8qzPx9Q%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071M5L?qs=VU8sRB4EgwAP38Z8qzPx9Q%3D%3D)                                                                                                                                     |
| R3, R9, R11, R31, R33                     | 5   | 18k               | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-1018KL?qs=qpJ%252B%252B%252Bdg6p1T2VMMxU7GeA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-1018KL?qs=qpJ%252B%252B%252Bdg6p1T2VMMxU7GeA%3D%3D)                                                                                                             |
| R4                                        | 1   | 200k              | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-10200KL?qs=x6vGwhDZZUbWpD4Ucl8tsQ%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-10200KL?qs=x6vGwhDZZUbWpD4Ucl8tsQ%3D%3D)                                                                                                                                   |
| R5                                        | 1   | 140k              | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07140KL?qs=IuGqVx9wL0ITcCE98xJS3Q%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07140KL?qs=IuGqVx9wL0ITcCE98xJS3Q%3D%3D)                                                                                                                                   |
| R8, R10, R36                              | 3   | 100k              | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100KL?qs=e1ok2LiJcmaihem8Va5%2Fsw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100KL?qs=e1ok2LiJcmaihem8Va5%2Fsw%3D%3D)                                                                                                                               |
| R26                                       | 1   | 5.6k              | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-075K6L?qs=2cAdsCoAWRHvOVv%2Fp%252BkS0g%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-075K6L?qs=2cAdsCoAWRHvOVv%2Fp%252BkS0g%3D%3D)                                                                                                                         |
| R27                                       | 1   | 100               | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100RL?qs=NEN%2FsE%2FLsvPIwIWKCOS4%2FA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100RL?qs=NEN%2FsE%2FLsvPIwIWKCOS4%2FA%3D%3D)                                                                                                                       |
| R30, R32                                  | 2   | 47k               | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-1047KL?qs=EiqXWrxQq600ZhhpLJs%252BtA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-1047KL?qs=EiqXWrxQq600ZhhpLJs%252BtA%3D%3D)                                                                                                                             |
| RA1A, RA1B                                | 2   | 510               | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07510RL?qs=gt6vzsuosg04lV7mPQHzdw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07510RL?qs=gt6vzsuosg04lV7mPQHzdw%3D%3D)                                                                                                                                   |
| RA3                                       | 1   | 270 (x4)          | 1206        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/TC164-JR-07270RL?qs=8cPjvKtxWv4v1GF6%2FXOmfA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/TC164-JR-07270RL?qs=8cPjvKtxWv4v1GF6%2FXOmfA%3D%3D)                                                                                                                               |
| SP                                        | 1   |                   |             | Speaker            | Can be salvaged from MGB/CGB instead                                                                              | [https://retrogamerepairshop.com/collections/gbp-audio/products/funnyplaying-clear-game-boy-color-speaker?variant=37728953761964](https://retrogamerepairshop.com/collections/gbp-audio/products/funnyplaying-clear-game-boy-color-speaker?variant=37728953761964)                                                           |
| SW1                                       | 1   |                   |             | Power switch       |                                                                                                                   | Salvaged (MGB/CGB)                                                                                                                                                                                                                                                                                                           |
| SW2                                       | 1   | COM-08184         |             | Navigation switch  |                                                                                                                   | [https://www.mouser.com/ProductDetail/SparkFun/COM-08184?qs=WyAARYrbSnYOIhcg6ARCiQ%3D%3D](https://www.mouser.com/ProductDetail/SparkFun/COM-08184?qs=WyAARYrbSnYOIhcg6ARCiQ%3D%3D)                                                                                                                                           |
| U1                                        | 1   | GBC CPU           | QFP-128     | CPU                |                                                                                                                   | Salvaged (GBC)                                                                                                                                                                                                                                                                                                               |
| U2                                        | 1   | LH52256CVTXIZ     | TSOP-28     | RAM                | Can be salvaged from CGB instead                                                                                  | [https://mou.sr/3f8G0Mi](https://mou.sr/3f8G0Mi)                                                                                                                                                                                                                                                                             |
| U3                                        | 1   | LM4853            | VSSOP-10    | Audio amplifier    |                                                                                                                   | [https://www.mouser.com/ProductDetail/Texas-Instruments/LM4853MM-NOPB?qs=QbsRYf82W3F2psFI2da2Dw%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/LM4853MM-NOPB?qs=QbsRYf82W3F2psFI2da2Dw%3D%3D)                                                                                                                 |
| U4                                        | 1   | NCP161ASN330T1G   | SOT23-5     | LDO                | Can also use TLV70233QDBVRQ1, probably                                                                            | [https://www.mouser.com/ProductDetail/863-NCP161ASN330T1G](https://www.mouser.com/ProductDetail/863-NCP161ASN330T1G)                                                                                                                                                                                                         |
| U5                                        | 1   |                   |             | Power Board        | Can also use other boards, see github for compatibility notes                                                     | [https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board](https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board)                                                                                                                                                                                                       |
| U6                                        | 1   | TPS3840DL35       | SOT23-5     | Supervisory IC     |                                                                                                                   | [https://www.mouser.com/ProductDetail/Texas-Instruments/TPS3840DL35DBVR?qs=7MVldsJ5UawbjRj7dP73rA%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/TPS3840DL35DBVR?qs=7MVldsJ5UawbjRj7dP73rA%3D%3D)                                                                                                             |
| U7                                        | 1   | TL331             | SOT23-5     | Comparator         |                                                                                                                   | [https://www.mouser.com/ProductDetail/Texas-Instruments/TL331KDBVT?qs=XGzIaZb%2FFYIdafwjPOKAMg%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/TL331KDBVT?qs=XGzIaZb%2FFYIdafwjPOKAMg%3D%3D)                                                                                                                   |
| VR1                                       | 1   | 10k (x2)          |             | Volume wheel       | Can be salvaged from MGB/CGB instead                                                                              | [https://retrogamerepairshop.com/collections/gbp-accessories/products/game-boy-pocket-color-contrast-volume-wheel-replacement?variant=37893894308012](https://retrogamerepairshop.com/collections/gbp-accessories/products/game-boy-pocket-color-contrast-volume-wheel-replacement?variant=37893894308012)                   |
| X1                                        | 1   | 8.388608MHz       | 7.5X5-4-PAD | Crystal oscillator |                                                                                                                   | Salvaged (GBC)                                                                                                                                                                                                                                                                                                               |

## Revision History

### v1.5 - Full Open Source Release (planned)

- Modify button contacts to feel more OEM-like
- Nudge SW2 to better fit in the shell, extend solder pads for easier assembly
- Flip locations of the up and down pads for the rocker switch
- Modify battery terminal contacts to match OEM style

### v1.4 - Beta III

- Adjust hole and part placement for better shell fitment
- Revert button contacts to Beta I design for better actuation
- Renamed some parts to match OEM descriptions
- Created separate v1.4S version

### v1.3 - Beta II

- Adjust hole and part placement for better shell fitment
- Changed button pads to mimic OEM
- Modified silkscreen to mimic OEM Game Boy PCBs better
- Change DC jack round holes to slots

### v1.2 - Beta I

- Restored OEM headphone jack
- Removed extra crystal oscillator pads (it won't fit in the shell)
- Shifted IPS screen kit connector down
- Removed load switch circuit and PTC input

### v1.1 - Alpha

- Changed name from MGBC-LCPU-01 to MGBC-MBL-01
- Flipped power switch to correct orientation
- Corrected power LED indicator dimming (v1.0 was backwards)
- Added pads for tactile buttons
- Added pads for different crystal oscillator package
- Changed headphone jack to new version instead of OEM

### v1.0 - Prototype

- Initial revision

## License
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>. You are able to copy and redistribute the material in any medium or format, as well as remix, transform, or build upon the material for any purpose (even commercial) - but you **must** give appropriate credit, provide a link to the license, and indicate if any changes were made.

©MouseBiteLabs 2023
