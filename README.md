# Game Boy Pocket Color (MGBC-MBL-01)

This repo is currently for the beta testers! Things are still generally unfinished here.

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

The master BOM with every electronic component required for the main MGBC circuit board is provided in the folder in Excel format. Note that some parts may be out of stock at the links provided, but many can be found at alternate other retailers online, or have a proper substitute. Here is a saved cart from Mouser that contains all the parts in the BOM Excel, including some duplicates. Double check to see if any parts are missing, and consider ordering multiples of some parts. Also, there are some parts you may want to remove (like the tactile switches).

**If a part is backordered, or out of stock** - check the Excel file, or the BOMs listed at the bottom of each board's folder in this repo. There may be alternate part options. You can also check for stock at places like Digikey. And you can always use Octopart.com to help find in-stock parts at other websites. I can't maintain the cart for every out-of-stock part, so please do some research :)

Also note, this BOM does not include parts for the Pocket Mouse Power Board. <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Please review my github on that board</a> for the parts information if you wish to use it for your power supply!

### III. Game Boy Electronic Parts

There are a handful of parts that I have not located aftermarket substitutes for, and will therefore necessitate an original Game Boy console to salvage from.

- The following parts from an original Game Boy Color console
  -	U1 - CGB CPU (all revisions *except* REV E, which is *incompatible*)
  - X1 – 8.388 MHz crystal oscillator
- The following parts from an original Game Boy Color **OR** Game Boy Pocket console
  -	P1 – Cartridge connector
  -	P5 - Headphone jack

The following parts can be salvaged from a Game Boy, but aftermarket options exist:

  - U2 - LH52256CVTXIZ; alternate: https://mou.sr/3f8G0Mi
  - EM10; alternate: https://mou.sr/3FiMvXw
  -	VR1 – Volume dial
  -	SW1 – Power switch
  -	P3 - Link port
  -	P4 - DC jack

### IV. External Build Parts

The following is the high-level BOM - basically, the Game Boy part. Note that parts that deviate from the ones listed here (like different shell designs) might necessitate different fitment modifications, or end up being incompatible. 

-	**Shell:** I generally recommend the Funnyplaying "IPS Ready" ones if you don't want to trim anything. If you don't use these, then you're on your own for how to prepare it - generally, you can follow guides for preparing a Pocket for an IPS screen kit.
    - RGRS: <a href="https://retrogamerepairshop.com/products/funnyplaying-game-boy-pocket-q5-ips-ready-shell-housing-no-cut?pr_prod_strat=copurchase&pr_rec_id=d8b0186ad&pr_rec_pid=6280907751596&pr_ref_pid=6115075391660&pr_seq=uniform">FunnyPlaying Game Boy Pocket IPS Backlight Ready Shell Housing No Cut</a>
-	**Screen Kit:** This is the important one. You need this specific type of kit - the Q5 IPS with OSD. It goes by many names, the maker is Hispeedido. Image below of what to look for. Laminated ones are *not* compatible, but kits that include a lit-up logo are fine to use. Make sure you DO NOT get the Game Boy Pocket version - it is not compatible!
    - RGRS: <a href="https://retrogamerepairshop.com/products/game-boy-color-q5-ips-backlight-with-osd?variant=37646279213228">GBC Q5 XL IPS Backlight with OSD</a>
    - HHL: <a href="https://handheldlegend.com/products/game-boy-color-ips-lcd-q5-hispeedido">Game Boy Color IPS LCD Q5 - Hispeedido</a>
    - AliExpress: <a href="https://www.aliexpress.us/item/3256801650459088.html?spm=a2g0o.productlist.main.1.758e53f17WUFK2&algo_pvid=24ef67e3-d608-4269-a663-05eafed1bd17&algo_exp_id=24ef67e3-d608-4269-a663-05eafed1bd17-0&pdp_npi=3%40dis%21USD%2145.9%2145.9%21%21%21%21%21%4021224e9b16816641208271256d074d%2112000017802039303%21sea%21US%210&curPageLogUid=dCymHIE0cr4X">GBC Q5 IPS LCD Kit</a>
-	**Lens:** I recommend you get an "IPS Lens" as the viewing area is slightly larger than the OEM one. 
    - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-lenses-1/products/funnyplaying-game-boy-pocket-ips-retro-pixel-mod-led-hole-glass-screen-lens?variant=37635319988396">FunnyPlaying Game Boy Pocket IPS Retro Pixel Mod LED Hole Glass Screen Lens</a>
- **Buttons:** Funnyplaying models are generally OEM-like (IMO), but you can also use OEM ones. Or any other maker of buttons! (Make sure you get Game Boy *Pocket* buttons.)
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-buttons-1/products/funnyplaying-game-boy-custom-pocket-buttons?variant=41432879169708">FunnyPlaying Game Boy Pocket Custom Buttons</a>
  - LabFifteen: <a href="https://labfifteenco.com/collections/game-boy-pocket-buttons">Custom buttons</a>
- **Membranes:** Important, but very forgettable! You will need them even if you install tactile switches.
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-buttons-1/products/funnyplaying-game-boy-pocket-silicone-button-contact-pad-membranes?variant=40593166401708">FunnyPlaying Game Boy Pocket Silicone Button Contact Pad Membranes
- **Speaker:** There are lots of options for this as well, including using the OEM one.
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-audio/products/funnyplaying-clear-game-boy-color-speaker?variant=37728953761964">FunnyPlaying Clear Game Boy Color & Pocket Speaker</a>

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

  - <a href="https://www.etsy.com/listing/1267252807/game-boy-color-battery-indicator-mod">Leggomyfroggo's Two-Stage Battery Indicator Mod</a>: goes in place of the power LED, changes color when battery gets low
  - <a href="https://www.etsy.com/listing/1422095615/frogulator-game-boy-colorpocket-dc">Leggomyfroggo's Frogulator</a>: a power supply that slots into the U5 socket; eyes light up for battery power indication
  - <a href="https://www.muramasaentertainment.com/product/pocket-power-pocket/">Muramasa's Pocket-Power Pocket</a>: an all-in-one LiPo charger including USB-C port; requires some shell cuts and **removal of EM7** [untested]
  - <a href="https://github.com/marshallh/gbpp">marshallh's Game Boy Pocket Power</a>: a power supply that slots into the U5 socket; has LiPo support (solder wires through the DC and BT+ holes on the MGBC board, and **remove EM7** - requires USB-C board for charging and some shell cuts [untested]
  - <a href="https://github.com/skimzor/SZ-REG">skimzor's SZ Regulator</a>: a power supply that slots into the U5 socket; customizable print on the front of the board through <a href="https://ko-fi.com/skimzor">skimzor's Ko-Fi page</a>
  - <a href="https://www.nataliethenerd.com/product-page/gbp-led-boards">Natalie the Nerd's LED Boards</a>: button LED backlight board

## Assembly Notes

![image](https://user-images.githubusercontent.com/97127539/219990501-9b55efcf-ba02-4d8f-96f3-af7368b2cbde.png)

1) Reset button capability
- Bridge the solder pads labeled RST (near bottom left of CPU) to turn the rocker switch into a reset button when you press the switch inwards.

![image](https://user-images.githubusercontent.com/97127539/219990759-c0daa3ab-4273-4972-9a4b-8c09f85be486.png)

2) Power LED brightness
- Change R9 to adjust the brightness (lower resistance, higher brightess; higher resistance, lower brightness)
- Change R10 to adjust the brightness when at low power (will always be dimmer than at regular power)

![image](https://user-images.githubusercontent.com/97127539/219990809-ff8819f6-2264-47de-baca-57e49f7fabfd.png)

3) Q5 Screen Kit Control (OSD, brightness, palette)
- Solder wires from the screen kit to the various pads on the top left corner of the board to control the screen kit
- A, B, and SEL are for the OSD controls, and BAT is for measuring the battery level
- "Up" and "Down" refer to the rocking direction on the rocker switch (where the contrast dial used to be) and are intended to be used with the touch-pads on the screen kit for controlling brightness and color palettes - desolder the touch pads, and in their place solder a wire on each to go from the kit to the MGBC board
- Try to keep the touch-pad wires as close to the board as possible after assembly - if they are touching the shell, then you can accidentally activate the touch controls

![image](https://user-images.githubusercontent.com/97127539/219991227-96a3e537-2404-4101-9735-b8606fba0f43.png)

Here is an example image from the DMGC project to give you an idea.

![image](https://user-images.githubusercontent.com/97127539/219991285-62322c20-a4b8-4ee3-8df7-6642a62ff0f1.png)

4) On the power board, make sure you short R2 with solder, and keep R3 depopulated. R2 is circled in red, R3 is circled in blue.

![image](https://user-images.githubusercontent.com/97127539/219991414-bc774b71-1174-4a31-b891-569e2c6f3b34.png)

5) If adding tactile switches, make note that start and select are rotated 90 degrees compared to the other buttons.

![image](https://user-images.githubusercontent.com/97127539/219991535-fd780568-689e-4bf6-9d48-6ef12466366d.png)

6) If you are adding a lipo with the GBPP, **REMOVE EM7**. (I haven't tested this yet.... so do so at your OWN RISK).

7) After you've assembled the PCBs, I suggest you test the output of the regulator board to make sure you are getting 5V out of the output pin *before* connecting it all to the main PCB. So, what you can do is just use wires instead of closer standoffs, and do not wire up the 5V output to the main board (5V output circled in red in the image below). Once you've checked that 5V is being output, then I would go ahead and solder the regulator board on properly.

![image](https://user-images.githubusercontent.com/97127539/220013209-31ed1b23-bfa9-404d-90dc-a969d6078904.png)

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
For these estimates, battery life is calculated using two eneloop pro NiMH AAS batteries (total of ~1860 mWh). Keep in mind that these are very rough estimates. I tried to be conservative in the power draw measurements, so hopefully these numbers represent a *mostly* worst case. Actual playtime *will* vary due to a variety of factors - changes in efficiency and performance as the battery voltage changes, differences in game audio, etc.

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

[audio]

### Original GBC Audio Spectrum

![image](https://user-images.githubusercontent.com/97127539/180213625-09bf0430-d7a2-47d9-acbe-a77910de87cb.png)

### MGBC Audio Spectrum

[image]
  
## PCB Bill of Materials

*These tables are provided above in an Excel format if it's easier to view. (Check the Board Assembly tab)*

Here's a table of the components you'll need for the PCB. Mouser cart with everything that isn't salvaged from an original board is here: https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=1970a339d8

I included multiples of all the passives, since they're small, and a few parts that are prone to being broken. I also added tactile switches to the order, which you can remove if you want the regular OEM feel without clicky buttons. 

Note: You do not need parts for the power board if you are using a GBPP, or Frogulator instead of my power board. I do not condone the use of Retrosix's Clean Power boards.

### Main PCB

| Reference Designators                | Qty | Value/Part Number | Package     | Description        | Comment                                                                                                           | Source                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------ | --- | ----------------- | ----------- | ------------------ | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| +, -                                 | 2   |                   |             | Battery terminals  | Can be salvaged from MGB instead                                                                                  | [https://retrogamerepairshop.com/collections/gbp-power/products/gbp-game-boy-pocket-high-quality-replacement-battery-contact-terminals?variant=37893131305132](https://retrogamerepairshop.com/collections/gbp-power/products/gbp-game-boy-pocket-high-quality-replacement-battery-contact-terminals?variant=37893131305132) |
| B1-B8                                | 8   | SKRRABE010        |             | Tactile switch     | Optional, can be omitted if you don't want clicky SP-style buttons (SKRRAA is less clicky, SKRRAC is more clicky) | [https://www.mouser.com/ProductDetail/688-SKRRAB](https://www.mouser.com/ProductDetail/688-SKRRAB)                                                                                                                                                                                                                           |
| C1                                   | 1   | 18pF              | 0603        | Capacitor (MLCC)   | Should be X5R (or better); at least 1% tolerance; at least 16V                                                    | [https://www.mouser.com/ProductDetail/YAGEO/CC0603FRNPO9BN180?qs=vTakOoo5QyL0KzYUzHPSUw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/CC0603FRNPO9BN180?qs=vTakOoo5QyL0KzYUzHPSUw%3D%3D)                                                                                                                                 |
| C2                                   | 1   | 27pF              | 0603        | Capacitor (MLCC)   | Should be X5R (or better); at least 1% tolerance; at least 16V                                                    | [https://www.mouser.com/ProductDetail/603-C0603FRNPO9BN270](https://www.mouser.com/ProductDetail/603-C0603FRNPO9BN270)                                                                                                                                                                                                       |
| C3, C16-C19, C39, C40, C48, C49, C51 | 10  | 1uF               | 0603        | Capacitor (MLCC)   | Should be X5R (or better), at least 16V                                                                           | [https://www.mouser.com/ProductDetail/KEMET/C0603C105K4RACTU?qs=STjISULpmtZNMAZGR4X39Q%3D%3D](https://www.mouser.com/ProductDetail/KEMET/C0603C105K4RACTU?qs=STjISULpmtZNMAZGR4X39Q%3D%3D)                                                                                                                                   |
| C4                                   | 1   | 22pF              | 0603        | Capacitor (MLCC)   |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/CC0603JRNPO9BN220?qs=vTakOoo5QyIVMYOUTI%2F4zA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/CC0603JRNPO9BN220?qs=vTakOoo5QyIVMYOUTI%2F4zA%3D%3D)                                                                                                                             |
| C5-C7                                | 3   | 100pF             | 0603        | Capacitor (MLCC)   |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/CC0603JPNPO9BN101?qs=7s%252B3O6pAiyAo%2FUxNqKltRA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/CC0603JPNPO9BN101?qs=7s%252B3O6pAiyAo%2FUxNqKltRA%3D%3D)                                                                                                                     |
| C8, C26, C27                         | 3   | 100uF             | 1206        | Capacitor (Tant)   | Experiment with different types if you want                                                                       | [https://www.mouser.com/ProductDetail/KYOCERA-AVX/TLJA107M006R0800?qs=o28%2FEEzBmj1LB376wnSl1g%3D%3D](https://www.mouser.com/ProductDetail/KYOCERA-AVX/TLJA107M006R0800?qs=o28%2FEEzBmj1LB376wnSl1g%3D%3D)                                                                                                                   |
| C9, C10, C29, C33, C41, C45          | 6   | 10nF              | 0603        | Capacitor (MLCC)   | Should be X5R (or better), at least 16V                                                                           | [https://www.mouser.com/ProductDetail/KEMET/C0603C103J5RACTU?qs=BimOss5pjlFJEfKhlb7g1g%3D%3D](https://www.mouser.com/ProductDetail/KEMET/C0603C103J5RACTU?qs=BimOss5pjlFJEfKhlb7g1g%3D%3D)                                                                                                                                   |
| C12, C24, C43, C52, C53              | 5   | 100nF             | 0603        | Capacitor (MLCC)   | Should be X5R (or better), at least 16V                                                                           | [https://www.mouser.com/ProductDetail/?qs=l5k%252BbMnNDknCtKnMv1oEgA%3D%3D](https://www.mouser.com/ProductDetail/?qs=l5k%252BbMnNDknCtKnMv1oEgA%3D%3D)                                                                                                                                                                       |
| C13, C14, C47                        | 3   | 150pF             | 0603        | Capacitor (MLCC)   |                                                                                                                   | [https://www.mouser.com/ProductDetail/KEMET/C0603C151J5GACTU?qs=V6nSPVTm7vxbAvL0weNH%252BQ%3D%3D](https://www.mouser.com/ProductDetail/KEMET/C0603C151J5GACTU?qs=V6nSPVTm7vxbAvL0weNH%252BQ%3D%3D)                                                                                                                           |
| D1                                   | 1   | PMEG2010AEH       | SOD-123     | Schottky diode     | Most schottky diodes should be suitable (at least 1A, 16V)                                                        | [https://www.mouser.com/ProductDetail/?qs=LOCUfHb8d9u7lcjEnyhX1g%3D%3D](https://www.mouser.com/ProductDetail/?qs=LOCUfHb8d9u7lcjEnyhX1g%3D%3D)                                                                                                                                                                               |
| EM2-EM4, EM9                         | 4   | BLM18BD102SN1D    | 0603        | Filter             |                                                                                                                   | [https://www.mouser.com/ProductDetail/Murata-Electronics/BLM18BD102SN1D?qs=h3IWXJJGQQWi4eZyJq6ScQ%3D%3D](https://www.mouser.com/ProductDetail/Murata-Electronics/BLM18BD102SN1D?qs=h3IWXJJGQQWi4eZyJq6ScQ%3D%3D)                                                                                                             |
| EM6-EM8                              | 3   | FBMH2012HM221-T   | 0805        | Filter             |                                                                                                                   | [https://www.mouser.com/ProductDetail/Taiyo-Yuden/FBMH2012HM221-T?qs=I6KAKw0tg2yIAV1HVl6Cew%3D%3D](https://www.mouser.com/ProductDetail/Taiyo-Yuden/FBMH2012HM221-T?qs=I6KAKw0tg2yIAV1HVl6Cew%3D%3D)                                                                                                                         |
| EM10                                 | 1   | 744235601         |             | Common mode filter | Can be salvaged from CGB instead                                                                                  | [https://www.mouser.com/ProductDetail/Wurth-Elektronik/744235601?qs=BXmE%252BJ0Y7xYO4MPd53j2NQ%3D%3D](https://www.mouser.com/ProductDetail/Wurth-Elektronik/744235601?qs=BXmE%252BJ0Y7xYO4MPd53j2NQ%3D%3D)                                                                                                                   |
| EXT                                  | 1   |                   |             | Link port          | Can be salvaged from MGB/CGB instead                                                                              | [https://retrogamerepairshop.com/collections/gbp-accessories/products/link-cable-replacement-port-for-gbc-gbp-gbl?variant=41808976183468](https://retrogamerepairshop.com/collections/gbp-accessories/products/link-cable-replacement-port-for-gbc-gbp-gbl?variant=41808976183468)                                           |
| F1                                   | 1   | 1A                | 1206        | Fuse               |                                                                                                                   | [https://www.mouser.com/ProductDetail/Vishay-Beyschlag/MFU1206FF01000P100?qs=oI046glRurt%252B%252B2FebA%252B66A%3D%3D](https://www.mouser.com/ProductDetail/Vishay-Beyschlag/MFU1206FF01000P100?qs=oI046glRurt%252B%252B2FebA%252B66A%3D%3D)                                                                                 |
| F2                                   | 1   | 1A                | 0603        | Fuse               |                                                                                                                   | [https://www.mouser.com/ProductDetail/Vishay-Beyschlag/MFU0603FF01000P100?qs=oI046glRurtlP8n%252B3l7CPg%3D%3D](https://www.mouser.com/ProductDetail/Vishay-Beyschlag/MFU0603FF01000P100?qs=oI046glRurtlP8n%252B3l7CPg%3D%3D)                                                                                                 |
| FB1                                  | 1   | BLA31AG601SN4D    | 1206        | Ferrite Bead       |                                                                                                                   | [https://www.mouser.com/ProductDetail/Murata-Electronics/BLA31AG601SN4D?qs=2ahBf5rJw09FDcUVkQibEg%3D%3D](https://www.mouser.com/ProductDetail/Murata-Electronics/BLA31AG601SN4D?qs=2ahBf5rJw09FDcUVkQibEg%3D%3D)                                                                                                             |
| J1                                   | 1   | 62684-502100AHLF  |             | LCD connector      |                                                                                                                   | [https://www.mouser.com/ProductDetail/?qs=HL%252BYNjdyZ0vzwc9E0QYY2g%3D%3D](https://www.mouser.com/ProductDetail/?qs=HL%252BYNjdyZ0vzwc9E0QYY2g%3D%3D)                                                                                                                                                                       |
| JACK                                 | 1   |                   |             | Headphone jack     |                                                                                                                   | Salvaged (MGB/CGB)                                                                                                                                                                                                                                                                                                           |
| LED1                                 | 1   | 151033RS03000     | 3mm         | Red LED            | Can be salvaged from MGB/CGB instead                                                                              | [https://www.mouser.com/ProductDetail/Wurth-Elektronik/151033RS03000?qs=LlUlMxKIyB1%252BAw6bWFN43w%3D%3D](https://www.mouser.com/ProductDetail/Wurth-Elektronik/151033RS03000?qs=LlUlMxKIyB1%252BAw6bWFN43w%3D%3D)                                                                                                           |
| P1                                   | 1   |                   |             | Cart connector     |                                                                                                                   | Salvaged (MGB/CGB)                                                                                                                                                                                                                                                                                                           |
| Q2                                   | 1   | MMBT3904          | SOT23       | NPN BJT            |                                                                                                                   | [https://www.mouser.com/ProductDetail/Nexperia/MMBT3904VL?qs=cnAQGvEIVkKbCwIpHJoHxQ%3D%3D](https://www.mouser.com/ProductDetail/Nexperia/MMBT3904VL?qs=cnAQGvEIVkKbCwIpHJoHxQ%3D%3D)                                                                                                                                         |
| R1, R11, R22, R23                    | 4   | 1k                | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071KL?qs=VU8sRB4EgwApHsk4rF%2F3zg%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071KL?qs=VU8sRB4EgwApHsk4rF%2F3zg%3D%3D)                                                                                                                                   |
| R2                                   | 1   | 3M                | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-073ML?qs=0yPvnVz5%2FmoE%252BprhggKQOw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-073ML?qs=0yPvnVz5%2FmoE%252BprhggKQOw%3D%3D)                                                                                                                           |
| R3, R10, R31, R33                    | 4   | 18k               | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-1018KL?qs=qpJ%252B%252B%252Bdg6p1T2VMMxU7GeA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-1018KL?qs=qpJ%252B%252B%252Bdg6p1T2VMMxU7GeA%3D%3D)                                                                                                             |
| R4, R36                              | 2   | 100k              | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100KL?qs=e1ok2LiJcmaihem8Va5%2Fsw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100KL?qs=e1ok2LiJcmaihem8Va5%2Fsw%3D%3D)                                                                                                                               |
| R5                                   | 1   | 300k              | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07300KL?qs=diQw95jMAeNfdIj8TA3yIQ%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07300KL?qs=diQw95jMAeNfdIj8TA3yIQ%3D%3D)                                                                                                                                   |
| R8                                   | 1   | 200k              | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07200KL?qs=VU8sRB4EgwCnxDNVmDU8zQ%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07200KL?qs=VU8sRB4EgwCnxDNVmDU8zQ%3D%3D)                                                                                                                                   |
| R9                                   | 1   | 4.7k              | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-074K7L?qs=gt6vzsuosg37y0l7Vt36bQ%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-074K7L?qs=gt6vzsuosg37y0l7Vt36bQ%3D%3D)                                                                                                                                     |
| R25                                  | 1   | 1.5M              | 0603        | Resistor           | Recommended at least 1% tolerance                                                                                 | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071M5L?qs=VU8sRB4EgwAP38Z8qzPx9Q%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071M5L?qs=VU8sRB4EgwAP38Z8qzPx9Q%3D%3D)                                                                                                                                     |
| R26                                  | 1   | 5.6k              | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-075K6L?qs=2cAdsCoAWRHvOVv%2Fp%252BkS0g%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-075K6L?qs=2cAdsCoAWRHvOVv%2Fp%252BkS0g%3D%3D)                                                                                                                         |
| R27                                  | 1   | 100               | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100RL?qs=NEN%2FsE%2FLsvPIwIWKCOS4%2FA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100RL?qs=NEN%2FsE%2FLsvPIwIWKCOS4%2FA%3D%3D)                                                                                                                       |
| R30, R32                             | 2   | 47k               | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-1047KL?qs=EiqXWrxQq600ZhhpLJs%252BtA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-1047KL?qs=EiqXWrxQq600ZhhpLJs%252BtA%3D%3D)                                                                                                                             |
| RA1A, RA1B                           | 2   | 510               | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07510RL?qs=gt6vzsuosg04lV7mPQHzdw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07510RL?qs=gt6vzsuosg04lV7mPQHzdw%3D%3D)                                                                                                                                   |
| RA3                                  | 1   | 270               | 0603        | Resistor           |                                                                                                                   | [https://www.mouser.com/ProductDetail/YAGEO/TC164-JR-07270RL?qs=8cPjvKtxWv4v1GF6%2FXOmfA%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/TC164-JR-07270RL?qs=8cPjvKtxWv4v1GF6%2FXOmfA%3D%3D)                                                                                                                               |
| S1                                   | 1   |                   |             | Power switch       |                                                                                                                   | Salvaged (MGB/CGB)                                                                                                                                                                                                                                                                                                           |
| S2                                   | 1   | COM-08184         |             | Navigation switch  |                                                                                                                   | [https://www.mouser.com/ProductDetail/SparkFun/COM-08184?qs=WyAARYrbSnYOIhcg6ARCiQ%3D%3D](https://www.mouser.com/ProductDetail/SparkFun/COM-08184?qs=WyAARYrbSnYOIhcg6ARCiQ%3D%3D)                                                                                                                                           |
| Speaker                              | 1   |                   |             | Speaker            | Can be salvaged from MGB/CGB instead                                                                              | [https://retrogamerepairshop.com/collections/gbp-audio/products/funnyplaying-clear-game-boy-color-speaker?variant=37728953761964](https://retrogamerepairshop.com/collections/gbp-audio/products/funnyplaying-clear-game-boy-color-speaker?variant=37728953761964)                                                           |
| DCJACK                               | 1   |                   | MGB-PWRJACK | DC Jack            |                                                                                                                   | Salvaged (MGB/CGB)                                                                                                                                                                                                                                                                                                           |
| U1                                   | 1   | GBC CPU           | QFP-128     | CPU                |                                                                                                                   | Salvaged (GBC)                                                                                                                                                                                                                                                                                                               |
| U2                                   | 1   | LH52256CVTXIZ     | TSOP-28     | RAM                | Replacement: https://mou.sr/3f8G0Mi                                                                               | Salvaged (GBC)                                                                                                                                                                                                                                                                                                               |
| U3                                   | 1   | LM4853            | VSSOP-10    | Audio amplifier    |                                                                                                                   | [https://www.mouser.com/ProductDetail/Texas-Instruments/LM4853MM-NOPB?qs=QbsRYf82W3F2psFI2da2Dw%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/LM4853MM-NOPB?qs=QbsRYf82W3F2psFI2da2Dw%3D%3D)                                                                                                                 |
| U4                                   | 1   | NCP161ASN330T1G   | SOT23-5     | LDO                | Can also use TLV70233QDBVRQ1, probably                                                                            | [https://www.mouser.com/ProductDetail/863-NCP161ASN330T1G](https://www.mouser.com/ProductDetail/863-NCP161ASN330T1G)                                                                                                                                                                                                         |
| U5                                   | 1   | TL331             | SOT23-5     | Comparator         |                                                                                                                   | [https://www.mouser.com/ProductDetail/Texas-Instruments/TL331KDBVT?qs=XGzIaZb%2FFYIdafwjPOKAMg%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/TL331KDBVT?qs=XGzIaZb%2FFYIdafwjPOKAMg%3D%3D)                                                                                                                   |
| U6                                   | 1   | TPS3840DL35       | SOT23-5     | Supervisory IC     |                                                                                                                   | [https://www.mouser.com/ProductDetail/Texas-Instruments/TPS3840DL35DBVR?qs=7MVldsJ5UawbjRj7dP73rA%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/TPS3840DL35DBVR?qs=7MVldsJ5UawbjRj7dP73rA%3D%3D)                                                                                                             |
| VR1                                  | 1   | 10k               |             | Volume wheel       | Can be salvaged from MGB/CGB instead                                                                              | [https://retrogamerepairshop.com/collections/gbp-accessories/products/game-boy-pocket-color-contrast-volume-wheel-replacement?variant=37893894308012](https://retrogamerepairshop.com/collections/gbp-accessories/products/game-boy-pocket-color-contrast-volume-wheel-replacement?variant=37893894308012)                   |
| X1                                   | 1   | 8.388608MHz       | 7.5X5-4-PAD | Crystal oscillator |                                                                                                                   | Salvaged (GBC)                                                                                                                                                                                                                                                                                                               |

### Power PCB

**Note:** R2 must be short circuited with a wire or solder blob, and R3 and C6 must be depopulated from the board entirely.

| Reference Designators | Qty           | Value/Part Number | Package | Description      | Comment                                 | Source                                                                                                                                                                                                                                         |
| --------------------- | ------------- | ----------------- | ------- | ---------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| C1, C3, C4, C5        | 4             | 10uF              | 0603    | Capacitor (MLCC) | Should be X5R (or better), at least 16V | [https://www.mouser.com/ProductDetail/Murata-Electronics/GRM188R61E106KA73J?qs=5aG0NVq1C4xEV8YyiSS7mg%3D%3D](https://www.mouser.com/ProductDetail/Murata-Electronics/GRM188R61E106KA73J?qs=5aG0NVq1C4xEV8YyiSS7mg%3D%3D)                       |
| C2, C12               | 2             | 100nF             | 0603    | Capacitor (MLCC) | Should be X5R (or better), at least 16V | [https://www.mouser.com/ProductDetail/?qs=l5k%252BbMnNDknCtKnMv1oEgA%3D%3D](https://www.mouser.com/ProductDetail/?qs=l5k%252BbMnNDknCtKnMv1oEgA%3D%3D)                                                                                         |
| C6                    | OPEN CIRCUIT  |
| C7                    | 1             | 1uF               | 0603    | Capacitor (MLCC) | Should be X5R (or better), at least 16V | [https://www.mouser.com/ProductDetail/KEMET/C0603C105K4RACTU?qs=STjISULpmtZNMAZGR4X39Q%3D%3D](https://www.mouser.com/ProductDetail/KEMET/C0603C105K4RACTU?qs=STjISULpmtZNMAZGR4X39Q%3D%3D)                                                     |
| L1                    | 1             | 2.2uH             | 1212    | Inductor         |                                         | [https://www.mouser.com/ProductDetail/Murata-Electronics/LQH3NPN2R2MMEL?qs=sJ5gq5MLFXqbWZz8NzZoog%3D%3D](https://www.mouser.com/ProductDetail/Murata-Electronics/LQH3NPN2R2MMEL?qs=sJ5gq5MLFXqbWZz8NzZoog%3D%3D)                               |
| LED1                  | 1             |                   | 0603    | Amber LED        |                                         | [https://www.mouser.com/ProductDetail/Wurth-Elektronik/150060AS75003?qs=sGAEpiMZZMt82OzCyDsLFPRX0KMcSqEwN27h33tWlGQ%3D](https://www.mouser.com/ProductDetail/Wurth-Elektronik/150060AS75003?qs=sGAEpiMZZMt82OzCyDsLFPRX0KMcSqEwN27h33tWlGQ%3D) |
| Q2                    | 1             | MMBT3904          | SOT23   | NPN BJT          |                                         | [https://www.mouser.com/ProductDetail/Nexperia/MMBT3904VL?qs=cnAQGvEIVkKbCwIpHJoHxQ%3D%3D](https://www.mouser.com/ProductDetail/Nexperia/MMBT3904VL?qs=cnAQGvEIVkKbCwIpHJoHxQ%3D%3D)                                                           |
| R1, R9                | 2             | 10k               | 0603    | Resistor         |                                         | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-0710KL?qs=grNVn54RoB%252B3GtjbJj3wJQ%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-0710KL?qs=grNVn54RoB%252B3GtjbJj3wJQ%3D%3D)                                               |
| R2                    | SHORT CIRCUIT |
| R3                    | OPEN CIRCUIT  |
| R4                    | 1             | 3M                | 0603    | Resistor         |                                         | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-073ML?qs=0yPvnVz5%2FmoE%252BprhggKQOw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-073ML?qs=0yPvnVz5%2FmoE%252BprhggKQOw%3D%3D)                                             |
| R5                    | 1             | 300k              | 0603    | Resistor         |                                         | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07300KL?qs=diQw95jMAeNfdIj8TA3yIQ%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07300KL?qs=diQw95jMAeNfdIj8TA3yIQ%3D%3D)                                                     |
| R6                    | 1             | 100k              | 0603    | Resistor         |                                         | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100KL?qs=e1ok2LiJcmaihem8Va5%2Fsw%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07100KL?qs=e1ok2LiJcmaihem8Va5%2Fsw%3D%3D)                                                 |
| R8                    | 1             | 200k              | 0603    | Resistor         |                                         | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07200KL?qs=VU8sRB4EgwCnxDNVmDU8zQ%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-07200KL?qs=VU8sRB4EgwCnxDNVmDU8zQ%3D%3D)                                                     |
| R11                   | 1             | 1k                | 0603    | Resistor         |                                         | [https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071KL?qs=VU8sRB4EgwApHsk4rF%2F3zg%3D%3D](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-071KL?qs=VU8sRB4EgwApHsk4rF%2F3zg%3D%3D)                                                     |
| U2                    | 1             | TPS61202          | WSON-10 | Boost Converter  |                                         | [https://www.mouser.com/ProductDetail/Texas-Instruments/TPS61202DSCR?qs=WxL8HmPi5r6YtrNaHRAS2Q%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/TPS61202DSCR?qs=WxL8HmPi5r6YtrNaHRAS2Q%3D%3D)                                     |
| U5                    | 1             | TL331             | SOT23-5 | Comparator       |                                         | [https://www.mouser.com/ProductDetail/Texas-Instruments/TL331KDBVT?qs=XGzIaZb%2FFYIdafwjPOKAMg%3D%3D](https://www.mouser.com/ProductDetail/Texas-Instruments/TL331KDBVT?qs=XGzIaZb%2FFYIdafwjPOKAMg%3D%3D)                                     |

  
## Frequently Asked Questions
  
I'll update this section as more people begin to build these. Please refer to this before asking me any questions!
  
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

This project is the culmination of nearly a full year of research, development, and testing. I have made this project completely open-source, and have put hundreds, if not *thousands* of hours of work into it, so that many people can enjoy it. **Please** give me appropriate credit where credit is due.

©MouseBiteLabs 2023
