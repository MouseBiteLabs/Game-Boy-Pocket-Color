# Game Boy Pocket Color

![image](https://user-images.githubusercontent.com/97127539/219991707-c83d69cf-715f-4326-8e82-952a977f087f.png)

My <a href="https://github.com/MouseBiteLabs/Game-Boy-DMG-Color">DMGC project</a> put a Game Boy Color put into an original Game Boy shell. But then I said, "Hey! This is neat, but I would rather it be small and cramped and have shorter battery life!" Enter the MGBC, or Pocket Color - a Game Boy Pocket (model name MGB) with the guts of a Game Boy Color (GBC). The PCB here is an original creation with some new features, though the concept and implementation of the "MGBC" or "Pocket Color" has been around for a while! Here are the project goals:

- A Game Boy Pocket aesthetic, using the original Game Boy Pocket shell and interfaces (link port, volume wheel, power switch, etc.), but with the capability of playing both Game Boy and Game Boy Color games.
- A nice, large IPS screen – the GBC Q5 XL IPS Backlight with OSD kit – with brightness and color palette control via the "navigation switch" housed where the contrast wheel used to be. (I will refer to the PCB attached to the Q5 screen as the “Q5 board”)
- A modernized, efficient switch mode power supply that can run off 2x AAA batteries or input from the DC jack, just like the original MGB. Testing shows that playing with NiMH AAA batteries can yield about 3.5 hours of gameplay at normal settings.
- Louder, cleaner sound through a modern audio amplifier.
- The option for tactile switches for the face buttons - like the GBA SP.
- No externally viewable case modifications.

All gerbers and source files can be found in this repo, as this project is fully open source. Technical documentation of the board can be found in the Technical folder. Please review the FAQ at the bottom of the README for answers to.... frequently asked questions.

## Disclaimer

Before I go any further, please read this VERY important disclaimer, if you are thinking about making this yourself.

I made this project first and foremost for my own purposes. Nearly all of the features I have included are things I personally wanted. I have tried my hardest to make the project modular, if others would like to improve or change things easily, and I have also tried very hard to make the design somewhat less prone to potential errors during assembly. But in the end, every decision I made was for what I wanted the final product to be, with my skill level in mind.

If you choose to build this project yourself, be warned - this is a considerably advanced, and expensive build. You must be comfortable with the fact that you may lose or damage expensive components. You are 100% liable for any damage done to your property or yourself. I am not responsible for any damage or loss of property incurred while attempting this project, or after completion of the project - you alone accept all risk. While I am confident in this design, I cannot claim full compatibility with every system configuration. And there may be latent issues that have yet to crop up. If you see anything I may have missed, or some dubious design choice, feel free to ask questions or comment as such - feedback is appreciated, corrections are welcome. You accept all risks and costs associated to this build if you choose to attempt it.

![image](https://user-images.githubusercontent.com/97127539/230615632-93c3e6fc-b554-4ee2-8f35-8e44d3867af7.png)

**DO NOT attempt this project if you are uncomfortable or inexperienced with detailed electronics troubleshooting, or are not proficient in soldering! You will AT MINIMUM need to be proficient in drag soldering and hot air reflowing. If you have not gained proficiency in these soldering skills, DO NOT ATTEMPT THIS PROJECT.**

## Bill of Materials (BOM)

There are a handful of categories for the parts you need for this build. Please review all of them! The total BOM cost will come out to anywhere between $120 and $200 (NOT including the cost of a donor Game Boy Color console!) depending on the options you choose and potential deals you can get on certain parts.

### I. Circuit Boards
  
First and foremost, you will need two brand new circuit boards for this build:
- <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/tree/main/MGBC%20PCB#mgbc-mbl-01">the main MGBC circuit board</a>, and 
- a power supply board that fits in the U5 socket on the MGBC board (like my <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Pocket Mouse Power Board</a>)

You can also use other power supply boards from other creators - check the "Compatibility with Other Mods" section below for more information. I don't recommend using an original power board from a Game Boy.

### II. Brand New Electronic Parts

The master BOM with every electronic component required for the main MGBC circuit board is provided in the folder in Excel format. Note that some parts may be out of stock at the links provided, but many can be found at alternate other retailers online, or have a proper substitute. Here is a saved cart from Mouser that contains all the parts in the BOM Excel, including some duplicates: https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=bc22c05d94

Double check to see if any parts are missing, and consider ordering multiples of some parts. Also, there are some parts you may want to remove (like the tactile switches). **If a part is backordered, or out of stock** - check the Excel file, or the separate BOMs for each circuit board assembly page. There may be alternate part options. You can also check for stock at places like Digikey. And you can always use Octopart.com to help find in-stock parts at other websites. I can't maintain the cart for every out-of-stock part, so please do some research :)

Also note, this BOM does not include parts for the Pocket Mouse Power Board. <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Please review my github on that board</a> for more information if you wish to use it for your power supply! The link to the saved cart for the power board can be found here: https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=39b200294d

### III. Game Boy Electronic Parts

There are a handful of parts that I have not located aftermarket substitutes for, and will therefore necessitate an original Game Boy console to salvage from. Please note that removing these parts is not a trivial task, and **requires advanced soldering and desoldering skills to be successful.**

- The following parts from an original Game Boy Color console
  -	U1 - CGB CPU (all revisions *except* REV E, which is *incompatible*)
  - X1 – 8.388 MHz crystal oscillator
- The following parts from an original Game Boy Color **OR** Game Boy Pocket console
  -	P1 – Cartridge connector
  -	P5 - Headphone jack

The following parts can be salvaged from a Game Boy, but aftermarket options exist:

  - U2 - LH52256CVTXIZ (SRAM); alternate: https://mou.sr/3f8G0Mi
  - EM10 - input filter; alternate: https://mou.sr/3FiMvXw
  -	VR1 – Volume dial
  -	SW1 – Power switch
  -	P3 - Link port
  -	P4 - DC jack

### IV. External Build Parts

The following is the high-level BOM - basically, the Game Boy part. Note that parts that deviate from the ones listed here (like different shell designs) might necessitate different fitment modifications, or end up being incompatible. 

-	**Shell:** I generally recommend the Funnyplaying "IPS Ready" ones if you don't want to trim anything. If you don't use these, then you're on your own for how to prepare it - generally, you can follow guides for preparing a Pocket for an IPS screen kit.
    - RGRS: <a href="https://retrogamerepairshop.com/products/funnyplaying-game-boy-pocket-q5-ips-ready-shell-housing-no-cut?pr_prod_strat=copurchase&pr_rec_id=d8b0186ad&pr_rec_pid=6280907751596&pr_ref_pid=6115075391660&pr_seq=uniform">FunnyPlaying Game Boy Pocket IPS Backlight Ready Shell Housing No Cut</a>
-	**Screen Kit:** This is the important one. You need this specific type of kit - the Q5 IPS with OSD. It goes by many names, the maker is Hispeedido. Laminated ones are *not* compatible, but kits that include a lit-up logo are fine to use. Make sure you DO NOT get the Game Boy Pocket version - it is not compatible!
    - RGRS: <a href="https://retrogamerepairshop.com/products/game-boy-color-q5-ips-backlight-with-osd?variant=37646279213228">GBC Q5 XL IPS Backlight with OSD</a>
    - HHL: <a href="https://handheldlegend.com/products/game-boy-color-ips-lcd-q5-hispeedido">Game Boy Color IPS LCD Q5 - Hispeedido</a>
    - AliExpress: <a href="https://www.aliexpress.us/item/3256801650459088.html?spm=a2g0o.productlist.main.1.758e53f17WUFK2&algo_pvid=24ef67e3-d608-4269-a663-05eafed1bd17&algo_exp_id=24ef67e3-d608-4269-a663-05eafed1bd17-0&pdp_npi=3%40dis%21USD%2145.9%2145.9%21%21%21%21%21%4021224e9b16816641208271256d074d%2112000017802039303%21sea%21US%210&curPageLogUid=dCymHIE0cr4X">GBC Q5 IPS LCD Kit</a>
-	**Lens:** I recommend you get an "IPS Lens" as the viewing area is slightly larger than the OEM one. 
    - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-lenses-1/products/funnyplaying-game-boy-pocket-ips-retro-pixel-mod-led-hole-glass-screen-lens?variant=37635319988396">FunnyPlaying Game Boy Pocket IPS Retro Pixel Mod LED Hole Glass Screen Lens</a>
- **Buttons:** Funnyplaying models are generally OEM-like (IMO), but you can also use OEM ones. Or any other maker of buttons! (Make sure you get Game Boy *Pocket* buttons - Game Boy *Color* buttons will not fit.)
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-buttons-1/products/funnyplaying-game-boy-custom-pocket-buttons?variant=41432879169708">FunnyPlaying Game Boy Pocket Custom Buttons</a>
  - LabFifteen: <a href="https://labfifteenco.com/collections/game-boy-pocket-buttons">Custom buttons</a>
- **Membranes:** Important, but very forgettable! You will need them even if you install tactile switches.
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-buttons-1/products/funnyplaying-game-boy-pocket-silicone-button-contact-pad-membranes?variant=40593166401708">FunnyPlaying Game Boy Pocket Silicone Button Contact Pad Membranes
- **Speaker:** There are lots of options for this as well, including using the OEM one.
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-audio/products/funnyplaying-clear-game-boy-color-speaker?variant=37728953761964">FunnyPlaying Clear Game Boy Color & Pocket Speaker</a>
- **Battery Tabs:** This one is another part I commonly forget about. You *cannot* use Game Boy Color ones, you *must* use Game Boy Pocket battery terminals. Luckily, they're very easy to find.
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-power/products/gbp-game-boy-pocket-high-quality-replacement-battery-contact-terminals?variant=37893131305132">GBP Game Boy Pocket High Quality Replacement Battery Contact Terminals

<b>Buying from RGRS? Consider helping out some cool people with these referral links:</b>
- <a href="https://retrogamerepairshop.com/?ref=ltyD2rUX">CodyWick</a>
- <a href="https://retrogamerepairshop.com/?ref=HSj4v5OO">JackV</a>

<b>Or use one of these discount codes at checkout:</b>
- Nataliethenerd
- B23N
- Tito

Note that the IPS kit I have listed is the *easiest* IPS kit to use that is compatible with this build. It includes an image centering feature, so you don't need to fiddle with centering it manually in the shell. Other kits likely would not center nicely in the DMG shell! <a href="https://retrogamerepairshop.com/collections/gbc-displays/products/game-boy-color-2-6-ips-high-brightness-drop-in-backlight-lcd-kit?variant=41398632251564">This kit works electrically, but requires you to center the image yourself.</a> If you end up making some sort of 3D-printed bracket to support this screen, feel free to share it here.  
  
### V. Compatibility with Other Mods

You don't need any extra mods to complete the MGBC build, but there are some options available. One of the goals for the MGBC was to provide compatibility with various mods by other makers. In general, I tried to make the board similar to the Game Boy Pocket PCB in terms of solder points for different kinds of mods. The MGBC will not benefit from any mods that include audio amplification/"cleaning" or tactile button mods, as I've included those improvements already. Check out the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/tree/main/MGBC%20PCB#customization-options">Customization Options</a> section in the MGBC PCB folder for information on those.
  
Here are a sample of my favorite mods for the MGBC:

  - <a href="https://www.etsy.com/listing/1267252807/game-boy-color-battery-indicator-mod">Leggomyfroggo's Two-Stage Battery Indicator Mod</a>: goes in place of the power LED, changes color when battery gets low
  - <a href="https://www.etsy.com/listing/1422095615/frogulator-game-boy-colorpocket-dc">Leggomyfroggo's Frogulator</a>: a power supply that slots into the U5 socket; eyes light up for battery power indication
  - <a href="https://www.muramasaentertainment.com/product/pocket-power-pocket/">Muramasa's Pocket-Power Pocket</a>: an all-in-one LiPo charger including USB-C port; requires some shell cuts and **removal of EM7** [untested]
  - <a href="https://github.com/marshallh/gbpp">marshallh's Game Boy Pocket Power</a>: a power supply that slots into the U5 socket; has LiPo support (solder wires through the DC and BT+ holes on the MGBC board, and **remove EM7** - requires USB-C board for charging and some shell cuts [untested]
  - <a href="https://github.com/skimzor/SZ-REG">skimzor's SZ Regulator</a>: a power supply that slots into the U5 socket; customizable print on the front of the board through <a href="https://ko-fi.com/skimzor">skimzor's Ko-Fi page</a>
  - <a href="https://www.nataliethenerd.com/product-page/gbp-led-boards">Natalie the Nerd's LED Boards</a>: button LED backlight board

## Testing and Assembly

I'm going to split this into a few separate sections. This is the general process I follow when assembling an MGBC.

### Circuit Board Assembly

Usually when I'm populating a board, I assemble all the non-Gameboy surface mount components first, not including C24, C29, and C45. After soldering these components, I solder the CPU in, then I use hot air and solder paste to reflow X1, C24, C29, and C45 onto the board. This seems to be the easiest way to go about assembling the components, for me anyway. 

[image of board]

For reference, here's a close-up view of the parts on the right hand side of the board - it's a bit cramped, I know, and the reference designators are not the easiest things to see.

[image]

If you are using a LiPo mod on the MGBC, **DO NOT INCLDE EM7**. This component must be removed from the final build.

[EM7 picture]

After the surface mount components are taken care of, I go on to add most of the rest of the components - VR1, P3, P4, P5, SW1, SW2, LED1, the speaker, and the battery terminals. The only parts that I don't populate at this point are the cartridge connector (P1) and the power board (U5). 

The next step to test is the power board, or U5. I *highly* suggest making sure you've assembled the power board correctly before directly connecting it and powering it all on, cowboy style. If you're able to test your power board before installation, definitely do that, but if you're not sure how, or don't have the ability, then you can use the MGBC board to test it. Just solder the board in the socket *except* for pin 7. Pin 7 is the 5 V pin, which powers the rest of the Game Boy. Keeping pin 7 depopulated, you can connect up batteries or a power supply, and turn the power switch on. Use a multimeter to measure the voltage from pin 7 (positive test probe) to GND (negative test probe). You should read approximately 5 V here - anything more than 5.1 V or less than 4.9 V means you've likely got something wrong on your power board. If you confirm you have 5 V on pin 7, you can go ahead and connect it up to the MGBC board (remove the batteries first, of course).

If you don't have 5 V out of pin 7 when testing this way, along with checking your power board assembly, you will also want to check to make sure the MGBC board doesn't have any issues. Read on...

### Troubleshooting Common Electrical Issues

I'm not going to delve into a lot of detail here, just some basic troubleshooting you can perform. Remember, this project is meant for those with experience in electronics assembly and troubleshooting, so you should be able to figure some of this out by yourself! These tips won't include simple things to check like "check for cold solder joints" or "make sure you have the right parts installed" and whatnot, but that doesn't mean that isn't your root cause!

**Issue: No power to U5 pins 1 or 2**

Are you getting voltage out of the batteries or DC jack? Measure the voltage across pin 2 of the U5 socket to GND - this should read whatever voltage your batteries or DC jack is outputting. Measuring the voltage from pin 1 of U5 to GND will give you the same result as pin 2 when the power switch is on, or zero volts when the power switch is off. 

If you get incorrect results, then check the following:
  - Make sure F1 or F2 are not blown. (Were you soldering when you had batteries installed? For shame!)
  - Check orientation of D1 - did you put it in backwards?
  - Check orientation of EM10 - is it 90 degrees rotated?
  - Check for a dirty DC jack (P4) - you should read nearly zero ohms with a resistance check across pins 2 and 3 when you don't have anything plugged in!
  - Make sure the batteries completely touch the battery terminals in the battery bay. This frequently happens to me in aftermarket shells without the battery separator.
  - Clean your power switch regardless of any issues, but if it's particularly dirty, you may not get any voltage reading on pin 1 even when it's turned on
  
**Issue: No sound or bad quality sound**

- Make sure C8, C26, and C27 are placed in the correct orientation. Remember, the stripe on tantalum capacitors indicates the POSITIVE side of the device.
- Plug in headphones to check if the issue is related to the speaker or both speaker and headphones. If you get audio out of your headphones but not your speaker, then:
  - Check for continuity from pin 5 on the headphone jack (top right corner when viewing from below) to GND. When headphones are not plugged in, this pin should be connected to ground. If it isn't, clean your headphone jack, or get another.
  - Try another speaker, if you have one.
- If your issue is both speaker *AND* headphones, then:
  - Clean your volume dial by dripping IPA in it and spinning it back and forth. Consider replacing it with a new aftermarket version.
  - Reflow components in the audio circuit and/or the CPU audio pins.
  
**Issue: White screen, glitchy display, miscolored display**

- Reflow the SRAM (U2) and make sure all pins are well-connected to the board.
- Reflow the FFC connector (P2) and make sure all pins are well-connected to the board.
- Reflow the CPU (U1) and make sure all pins are well-connected to the board.
- If miscolored, make sure the palette isn't being cycled on the IPS kit, as there is a touchpad that cycles through different color modes.

### Final Assembly

Before assembling the board into the shell, I prepared the Q5 board solder pads. I cut six 30 gauge wire segments and soldered them on the brightness, palette, battery, and OSD input pads. These will be soldered to the top of the board after the screen is installed.

![image](https://user-images.githubusercontent.com/97127539/184281803-ea1ec2ce-f2cf-489f-90db-754a21dc3f10.jpg)

Next, I finished the build. The end.

## Auxilliary Controls
### Q5 XL IPS Backlight with OSD
-	Select + A + B: Open the OSD menu
-	Select + A: Enter
-	Select + B: Exit
-	A: Increase
-	B: Decrease

### Navigation Switch
-	Rock up: Advance screen brightness setting
-	Rock up/Hold: Toggle on-screen battery indicator
-	Rock down: Advance screen color pallete setting
-	Rock down/Hold: Toggle on-screen pixel grid
-	Push in: System reset
  
## Power Draw Measurements
For these estimates, battery life is calculated using two eneloop pro NiMH AA batteries (total of ~1860 mWh). Keep in mind that these are very rough estimates. I tried to be conservative in the power draw measurements, so hopefully these numbers represent a *mostly* worst case. Actual playtime *will* vary due to a variety of factors - changes in efficiency and performance as the battery voltage changes, differences in game audio, etc.

| Test Criteria | Power Draw | Estimated Battery Life |
| ------------- | ------------- | ------------- |
| IPS max brightness, speaker volume 100%, Everdrive X5	| mW | hr |
| IPS max brightness, speaker volume 100%, original cartridge | mW | hr |
| IPS med brightness, headphones, Everdrive X5	| mW	| hr |
| IPS med brightness, speaker volume 100%, original cartridge | mW	| hr |
| IPS min brightness, headphones, original cartridge	| mW	| hr |

## Audio Recordings and Spectrum
For these results, I connected the headphone jack to my computer's microphone input, and used Audacity to obtain line out recordings. Then I graphed the spectrum using Audacity's "plot spectrum" analysis tool. You can see the larger gain at the lower frequencies in the spectrum plot of the MGBC, similar to the results from my DMGC project. I'm pretty sure the MGBC all-around sounds nicer than a stock system, at least through headphones. Listen for yourself! (GitHub only allows for video files to be embedded, MP3 files are provided above)

### Original GBC Audio

https://user-images.githubusercontent.com/97127539/180215249-4b21aca1-a9fd-430a-a870-95bf4837e4da.mp4

### MGBC Audio

https://user-images.githubusercontent.com/97127539/232619867-ac0df1a6-45e1-47b4-a0c2-0df85b547195.mp4

### Original GBC Audio Spectrum

![image](https://user-images.githubusercontent.com/97127539/180213625-09bf0430-d7a2-47d9-acbe-a77910de87cb.png)

### MGBC Audio Spectrum

![image](https://user-images.githubusercontent.com/97127539/232620578-6f7e4e28-bd64-4657-a0e6-ce16f42ecdb7.png)
  
## Frequently Asked Questions
  
I'll update this section as more people begin to build these. Please refer to this before asking me any questions! If you ask me a question, I'm going to automatically ask you if you read the FAQ and this entire repo first.
  
**Q: Can you make one for me?**
  
A: NO. Stop asking, please!
  
**Q: Why are you encouraging the destruction of Game Boys?**
  
A: If you can properly complete this mod, you will have destroyed zero Game Boys, as you get a working Game Boy when you finish.
  
**Q: Aren't you contributing to the rising prices of Game Boys by doing this?**
  
A: <a href="https://en.wikipedia.org/wiki/Game_Boy_Color#:~:text=The%20Game%20Boy%20and%20Game,game%20console%20of%20all%20time.">There were over 100,000,000 Game Boy Colors sold around the world.</a> So, no, not in any appreciable manner.

**Q: My EM10 has an extra leg in-between two of the other ones. Can I use this part?**

A: Yes, just bend up the extra pin so that it doesn't contact any of the nearby pads. It is an unused anchor pin.

**Q: Sometimes the power switch is finnicky and the system won't power on consistently. Sometimes the IPS screen will turn on, but only the backlight, not the actual image. What gives?**

A: <a href="https://www.youtube.com/watch?v=2_Pt_odHyzo">Clean your power switch.</a> This fixes most issues. Do it properly - if you're attempting this mod, you should be able to properly clean your power switch.

**Q: I'm using a battery holder with alligator clips to test the system, and it's not turning on. Why?**
  
A: I've found that sometimes the contact resistance from the alligator clips was enough to prevent the system from powering up properly. Try putting the board in the shell and inserting the batteries in the back normally.
  
## Acknowledgements

- <a href="https://github.com/MouseBiteLabs/Game-Boy-DMG-Color#acknowledgements">Thanks to everyone I already thanked for the technical support and resources for my DMGC project,</a> as most of the work I did on that was directly applicable to this one.
- VERY special thanks to all the alpha and beta testers who took time and money to build boards and give me extremely useful feedback on the design. You made the final product better than I could have done on my own.
- Thanks to the awesome members of the <a href="https://moddedgameboy.club/">Modded Gameboy Club</a> for their feedback and support during the entire project development.
- Thank you to skimzor for support on the initial layout, providing me with reference measurements for all the external components, like the power switch and volume wheel. <a href="https://github.com/skimzor/SZ-POCO">Check out his own Pocket Color boards!</a>
-	Of course, huge thank you to everyone who has <a href="https://ko-fi.com/bucketmouse">donated and supported me</a>, and to those who have built their own MGBC! I love seeing pictures of builds, so feel free to share them with me on Twitter, <a href="https://discord.gg/Y5aDvCcpbX">discord</a>, or via email!

## License
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>. You are able to copy and redistribute the material in any medium or format, as well as remix, transform, or build upon the material for any purpose (even commercial) - but you **must** give appropriate credit, provide a link to the license, and indicate if any changes were made.

This project is the culmination of over a full year of research, development, and testing. I have made this project completely open-source, and have put hundreds, if not *thousands* of hours of work (and dollars!) into it, so that many people can enjoy it. **Please** give me appropriate credit where credit is due.

©MouseBiteLabs 2023
