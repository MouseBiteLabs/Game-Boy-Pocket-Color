# MGBC-MBL-01

[board scans]

This is the main circuit board in the MGBC build. It houses everything except the main power supply (referred to as U5). This README will provide instructions for how to customize the build to your liking, as well as attempt to clear up any questions you may have about the build process.

## Board Characteristics

The zipped folder contains all the gerber files for this board, if you wish to order it from a board manufacturer yourself.

-	Layers: 2
-	Thickness: 1 mm
-	Surface Finish: ENIG or HASL
-   **NOTE: When ordering PCBs, add this note to the order: "The file milling.gbr contains outlines for plated slots. Please add plated slots on the PCB according to this layer."**

*HASL will work, but will potentially be more difficult for soldering fine-pitch parts like the CPU and FFC connector. 
ENIG is required for reliable button press detection; you can use HASL if you are using tactile switches.*

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

### Enabling Reset Button Functionality

Bridge the pads labelled "RST" with solder to turn the navigation switch into a reset button whenever you push it in. It's not particularly easy to push the button in, so accidental resets shouldn't be a concern. But if you find yourself accidentally resetting the system, you can remove the solder from the pads to disable it.

[IMAGE]

### Power LED Brightness

Increase the value of R1 to decrease the brightness of the power LED during normal battery levels. Increase the value of R2 to decrease the brightness of the power LED during low battery levels. It is suggested to try changing resistances in ~5 kΩ increments.

[IMAGE]

### Tactile Switches

If you want clicky buttons, like the GBA SP has, then you can install tactile switches onto the button contacts. These are listed as B1-B8 on the BOM. There are three levels of clickiness to choose from, depending on the part number you select - SKRRAAE010 is the "least clicky" with 1 N operating force, SKRRABE010 has 1.6 N of operating force, and SKRRACE010 is the "most clicky" with 2 N of operating force. Note when installing the switches to make sure the little "wings" are oriented correctly as indicated on the board!

[IMAGE]

### LiPo Support

Are you using the Game Boy Pocket Power regulator for U5 for LiPo support? If so, solder wires or headers from the DC and BT+ holes into the GBPP, thread the wires from the battery through the hole in the board to the GBPP connections, and remember to **REMOVE EM7**. You'll also need a USB-C adapter PCB to go in place of DC jack.

[IMAGE]

## Bill of Materials

This should be for reference only. This can be found in the main folder in Excel format. There is also a link in the main folder for a saved Mouser cart with all these parts.

[Table]

## Revision History

### v1.4 - Release

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
