# Game Boy Pocket Color

![image](https://user-images.githubusercontent.com/97127539/219991707-c83d69cf-715f-4326-8e82-952a977f087f.png)

My <a href="https://github.com/MouseBiteLabs/Game-Boy-DMG-Color">DMGC project</a> put a Game Boy Color put into an original Game Boy shell. But then I said, "Hey! This is neat, but I would rather it be small and cramped and have shorter battery life!" Enter the MGBC, or Pocket Color - a Game Boy Pocket (model name MGB) with the guts of a Game Boy Color (GBC). The PCB here is an original creation with some new features, though the concept and implementation of the "MGBC" or "Pocket Color" has been around for a while! Here are the project goals:

- A Game Boy Pocket aesthetic, using the original Game Boy Pocket shell and interfaces (link port, volume wheel, power switch, etc.), but with the capability of playing both Game Boy and Game Boy Color games.
- A nice, large IPS screen – the GBC Q5 XL IPS Backlight with OSD kit – with brightness and color palette control via the "navigation switch" housed where the contrast wheel used to be. (I will refer to the PCB attached to the Q5 screen as the “Q5 board”)
- A modernized, efficient switch mode power supply that can run off 2x AAA batteries or input from the DC jack, just like the original MGB. Testing shows that playing with NiMH AAA batteries can yield about 3.5 hours of gameplay at normal settings.
- Louder, cleaner sound through a modern audio amplifier.
- The option for tactile switches for the face buttons - like the GBA SP.
- No major externally viewable case modifications, to keep the OEM look and feel, outside of the screen, as much as possible.

All gerbers and source files can be found in this repo, as this project is fully open source. These PCB files and notes about the board, including customizations **and some troubleshooting tips**, can be found in the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/tree/main/MGBC%20PCB#cpu-pin-functions">PCB folder</a>. Technical documentation of the board can be found in the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/tree/main/Technical">Technical folder</a>.

**Do you want to make one?** Then you NEED TO READ this entire page. Seriously. Before asking a question, please review the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color#frequently-asked-questions">FAQ</a> at the bottom of the README for answers to.... frequently asked questions. Please try to find your answer in this repository - 95% of the time someone asks me something it's answered here already.

## Disclaimer

Before I go any further, please read this VERY important disclaimer, **IN IT'S ENTIRETY,** if you are thinking about making this yourself. **Don't let this picture happen to you!**

![image](https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/assets/97127539/a5462f7a-fef0-465b-abce-b6d332485d08)

I made this project first and foremost for my own purposes. Nearly all of the features I have included are things I personally wanted. I have tried my hardest to make the project modular, if others would like to improve or change things easily, and I have also tried very hard to make the design somewhat less prone to potential errors during assembly. But in the end, every decision I made was for what I wanted the final product to be, with my skill level in mind.

So if you choose to build this project yourself, be warned - this is a considerably advanced, and expensive build. You must be comfortable with the fact that you may lose or damage expensive components. You are 100% liable for any damage done to your property or yourself. I am not responsible for any damage or loss of property incurred while attempting this project, or after completion of the project - you alone accept all risk. If you're *at all* questioning wether or not you can successfully attempt this project, please first practice with the <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Pocket Mouse Power Board</a> - this requires no original Game Boy parts, and the total parts cost of the board is less than $10. And before you dismantle a Game Boy, solder the FFC connector on the top of the MGBC board to make sure you are comfortable with long rows of fine pitch pins, as it is the same pin pitch as the much more expensive and important CPU. **If you have any difficulty assembling either the power board or the FFC connector, I highly discourage attempting the rest of the build.**

Furthermore, while I am confident in this design, I cannot claim full compatibility with every system configuration. **Especially if you decide to add a lithium-ion battery.** And there may be latent issues that have yet to crop up. If you see anything I may have missed, or some dubious design choice, feel free to ask questions or comment as such - feedback is appreciated, corrections are welcome.

![image](https://user-images.githubusercontent.com/97127539/230615632-93c3e6fc-b554-4ee2-8f35-8e44d3867af7.png)

In summation: **DO NOT attempt this project if you are uncomfortable or inexperienced with detailed electronics troubleshooting, or are not proficient in soldering! This is in NO WAY a beginner's project. You will AT MINIMUM need to be proficient in <a href="https://youtu.be/5uiroWBkdFY?t=110">drag soldering</a> and <a href="https://youtu.be/X3Rc1s6EpSI">hot air reflowing</a>. If you have not gained proficiency in these soldering skills, DO NOT ATTEMPT THIS PROJECT. You accept all risks and costs associated to this build if you choose to attempt it.**

(These parts are *tiny*. Quarter for scale - do not install a quarter in your final build.)

![image](https://user-images.githubusercontent.com/97127539/235316631-477d5fd4-df52-48bd-8271-00153829703f.png)

## Bill of Materials (BOM)

There are a handful of categories for the parts you need for this build. Please review all of them! The total BOM cost will come out to anywhere between $100 and $200 (NOT including the cost of a donor Game Boy Color console!) depending on the options you choose, which OEM parts you re-use, and any potential deals you can get on certain parts. Note that with the exception of a few components from a donor Game Boy Color, *most* of the electronic parts are brand new.

### I. Circuit Boards
  
First and foremost, you will need two brand new circuit boards for this build:
- <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/tree/main/MGBC%20PCB#mgbc-mbl-01">the main MGBC circuit board</a>, and 
- a power supply board that fits in the U5 socket on the MGBC board (like my <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Pocket Mouse Power Board</a>)

Again, I sell <a href="https://mousebitelabs.etsy.com/listing/1459241814/game-boy-pocket-color-pcb-mgbc-mbl-01?utm_source=Copy&utm_medium=ListingManager&utm_campaign=Share&utm_term=so.lmsm&share_time=1694127166906">the MGBC board</a> and <a href="https://mousebitelabs.etsy.com/listing/1473483915/pocket-mouse-power-board?utm_source=Copy&utm_medium=ListingManager&utm_campaign=Share&utm_term=so.lmsm&share_time=1694127201480">my regulator board</a> on my Etsy store. You can alternatively use the files in the MGBC PCB folder to order it yourself. Please see the MGBC PCB folder for more info.

<a href="https://mousebitelabs.etsy.com/listing/1459241814/game-boy-pocket-color-pcb-mgbc-mbl-01?utm_source=Copy&utm_medium=ListingManager&utm_campaign=Share&utm_term=so.lmsm&share_time=1694127166906"><img src="https://github-production-user-asset-6210df.s3.amazonaws.com/97127539/239718536-5c9aefe3-0628-4434-b8d8-55ff80ac3bbc.png" alt="PCB from Etsy" /></a> 

You can also use other power supply boards from other creators - check the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color#v-compatibility-with-other-mods">Compatibility</a> section below for more information. 

**I don't recommend using an original power board from a Game Boy!**

### Information on Older Revisions

The current revision is v2.0, but you may have an earlier board (if you bought one from me, rest assured it will work perfectly fine - most of the changes between for-sale revisions are inconsequential to the end user). The BOM has changed slightly for v1.6 and later boards, compared to previous revisions. Please view the Excel and/or .csv file above for BOM information (or contact me). Here's a short list of information about the older boards, and what is required/recommended when using them:

| Revision | Recommendations |
| ---- | ---------------------------------------------------------------------------------------------------------------------------- |
| v1.0 | You are a masochist. You're on your own for this one.                                                                        |
| v1.1 | Are you me? No? Then did you rob my house?                                                                                   |
| v1.2 | You're one of the beloved beta testers. You didn't build it yet? For shame. Contact me.                                      |
| v1.3 | These should be practice boards only.                                                                                        |
| v1.4 | Use tactile buttons. Minor shell trimming may be required for volume dial and rocker switch.                                 |
| v1.5 | Minor shell trimming may be required for volume dial and rocker switch.                                                      |
| v1.6 | No important differences compared to v2.0.                                                                                   |

### II. Brand New Electronic Parts

The MGBC board uses mostly all-new components. This is not a direct-transfer board. The master BOM with every electronic component required for the main MGBC circuit board is provided in the folder in Excel format. Note that some parts may be out of stock at the links provided, but many can be found at alternate other retailers online, or have a proper substitute. Here is a saved cart from Mouser that contains all the parts in the BOM Excel, including some duplicates: https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=854e7f6cf9

*Note: This cart link is for v1.6 and v2.0 boards. Please check out the BOM Excel or .csv file above for information about v1.5 and earlier.*

Double check to see if any parts are missing, and consider ordering multiples of some parts. Also, there are some parts you may want to remove (like the tactile switches). **If a part is backordered, or out of stock** - check the Excel file, or the BOM listed at the bottom of the MGBC PCB folder. There may be alternate part options listed. You can also check for stock at places like Digikey, Newark, or LCSC. And you can always use Octopart.com to help find in-stock parts at other websites. Please understand that I can't maintain the cart for every out-of-stock part, so please do some research :)

Also note, while I do recommend the board, this BOM does not include parts for the Pocket Mouse Power Board. <a href="https://github.com/MouseBiteLabs/Pocket-Mouse-Power-Board">Please review my github on that board</a> for more information if you wish to use it for your power supply!

### III. Game Boy Electronic Parts

*Despite this being a **Pocket** Color, you don't actually need a Game Boy Pocket. However, this project **does require** at minimum a Game Boy Color.*

There are a handful of parts that I have not located aftermarket substitutes for, and will therefore necessitate an original Game Boy console to salvage from. Please note that removing these parts is not a trivial task, and **requires advanced soldering and desoldering skills to be successful.**

The following parts are required from an original Game Boy Color console:

  -	U1 – CGB CPU (all revisions *except* REV E, which is *incompatible*)
  - X1 – 8.388 MHz crystal oscillator

The following parts are required from an original Game Boy Color **OR** Game Boy Pocket console:

  -	P1 – Cartridge connector
  -	P5 – Headphone jack

The following parts can be salvaged from a Game Boy Color, but newly manufactured commercial off-the-shelf options exist:

  - U2 – LH52256CVTXIZ (SRAM); alternate: https://mou.sr/3f8G0Mi
  - EM10 – input filter; alternate: https://mou.sr/3FiMvXw

The following parts can be salvaged from a Game Boy Color *or* Game Boy Pocket, but aftermarket options exist:

  -	VR1 – Volume dial
  -	SW1 – Power switch
  -	P3 – Link port
  -	P4 – DC jack

### IV. External Build Parts

The following is the high-level BOM - basically, the Game Boy part. Note that parts that deviate from the ones listed here (like different shell designs) might necessitate different fitment modifications, or end up being incompatible. Note that this list is not a comprehensive list of all the places you can get these parts. I encourage you to search around if you can't find what you want here. 

-	**Shell:** I generally recommend the Funnyplaying "IPS Ready" ones if you don't want to trim anything. If you don't use these, then you're on your own for how to prepare it - generally, you can follow guides for preparing a Pocket for an IPS screen kit.
    - RGRS: <a href="https://retrogamerepairshop.com/products/funnyplaying-game-boy-pocket-q5-ips-ready-shell-housing-no-cut?pr_prod_strat=copurchase&pr_rec_id=d8b0186ad&pr_rec_pid=6280907751596&pr_ref_pid=6115075391660&pr_seq=uniform">FunnyPlaying Game Boy Pocket IPS Backlight Ready Shell Housing No Cut</a>
    - FunnyPlaying: <a href="https://funnyplaying.com/collections/product/products/gbp-retro-pixel-ips-coustom-shell?variant=33054643060797">GBP RETRO PIXEL IPS CUSTOM SHELL</a>
-	**Screen Kit:** This is the important one. You need this specific type of kit - the Q5 IPS with OSD. It goes by many names, the maker is Hispeedido (*not* FunnyPlaying). Kits that have the screen laminated to a GBC lens are *not* compatible, but kits that include a lit-up logo on the bottom part of the screen are fine to use. Make sure you DO NOT get the Game Boy Pocket version - it is not compatible! Also, be sure to test this screen kit before installing it, preferrably with an original Game Boy Color. Sometimes they arrive damaged, and once you've installed, it may not be possible to get a refund.
    - RGRS: <a href="https://retrogamerepairshop.com/products/game-boy-color-q5-ips-backlight-with-osd?variant=37646279213228">GBC Q5 XL IPS Backlight with OSD</a> OR <a href="https://retrogamerepairshop.com/collections/gbc-displays/products/game-boy-color-q5-osd-ips-kit-with-color-changing-logo?variant=41819042185388">Game Boy Color Q5 OSD IPS Kit with Color Changing Logo 
    - AliExpress: <a href="https://www.aliexpress.us/item/3256801650459088.html?spm=a2g0o.productlist.main.1.758e53f17WUFK2&algo_pvid=24ef67e3-d608-4269-a663-05eafed1bd17&algo_exp_id=24ef67e3-d608-4269-a663-05eafed1bd17-0&pdp_npi=3%40dis%21USD%2145.9%2145.9%21%21%21%21%21%4021224e9b16816641208271256d074d%2112000017802039303%21sea%21US%210&curPageLogUid=dCymHIE0cr4X">GBC Q5 IPS LCD Kit</a>
    - HHL: <a href="https://handheldlegend.com/products/game-boy-color-ips-lcd-q5-hispeedido">Game Boy Color IPS LCD Q5 - Hispeedido</a>
I have not thoroughly tested it, but the CGS (Cloud Game Store) display should be electrically compatible as of v2.0. It will need some kind of method of centering the image if you choose to use it, though. (At the time of writing, I have heard there is a seller on Taobao selling laminated CGS kits...)
  -	**Lens:** I recommend you get an "IPS Lens" as the viewing area is slightly larger than the OEM one. 
    - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-lenses-1/products/funnyplaying-game-boy-pocket-ips-retro-pixel-mod-led-hole-glass-screen-lens?variant=37635319988396">FunnyPlaying Game Boy Pocket IPS Retro Pixel Mod LED Hole Glass Screen Lens</a>
    - FunnyPlaying: <a href="https://funnyplaying.com/products/gbp-retro-pixel-ips-glass-lens?_pos=1&_sid=ec7345577&_ss=r&variant=31969857437757">GBP RETRO PIXEL IPS GLASS LENS</a>
- **Buttons:** Funnyplaying models are generally OEM-like (IMO), but you can also use OEM ones. Or any other maker of buttons! (Make sure you get Game Boy *Pocket* buttons - Game Boy *Color* buttons will not fit.)
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-buttons-1/products/funnyplaying-game-boy-custom-pocket-buttons?variant=41432879169708">FunnyPlaying Game Boy Pocket Custom Buttons</a>
  - LabFifteen: <a href="https://labfifteenco.com/collections/game-boy-pocket-buttons">Custom buttons</a>
  - FunnyPlaying: <a href="https://funnyplaying.com/products/gbp-custom-buttons?_pos=2&_sid=1bdf0ccb6&_ss=r&variant=33054652039229">GBP CUSTOM BUTTONS</a>
- **Membranes:** Important, but very forgettable! You will need them even if you install tactile switches.
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-buttons-1/products/funnyplaying-game-boy-pocket-silicone-button-contact-pad-membranes?variant=40593166401708">FunnyPlaying Game Boy Pocket Silicone Button Contact Pad Membranes
  - FunnyPlaying: <a href="https://funnyplaying.com/products/replacement-silicone-pads-for-gbp-mgb?_pos=3&_sid=1bdf0ccb6&_ss=r&variant=39378004705341">GBP/MGB REPLACEMENT SILICONE PADS</a>
- **Speaker:** There are tons of options for this as well, including using the OEM one. Game Boy Color *and* Game Boy Pocket speakers are compatible, since they are the same part.
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-audio/products/funnyplaying-clear-game-boy-color-speaker?variant=37728953761964">FunnyPlaying Clear Game Boy Color & Pocket Speaker</a>
  - FunnyPlaying: <a href="https://funnyplaying.com/products/clear-gbc-mgb-speaker?_pos=1&_sid=2cc6157b6&_ss=r">CLEAR GBC/MGB SPEAKER</a>
- **Battery Tabs:** This one is another part I commonly forget about. You *cannot* use Game Boy Color ones, you *must* use Game Boy Pocket battery terminals. Luckily, they're very easy to find.
  - RGRS: <a href="https://retrogamerepairshop.com/collections/gbp-power/products/gbp-game-boy-pocket-high-quality-replacement-battery-contact-terminals?variant=37893131305132">GBP Game Boy Pocket High Quality Replacement Battery Contact Terminals
- **Stickers:** Completely optional, but they can really bring a build together. Especially if you have custom Pocket Color stickers!
  - Nextstopplease: <a href="https://nextstopplease.square.site/product/gb-pocket-color-label/196?cp=true&sa=true&sbp=false&q=false">GB Pocket Color Label</a>
  - 8bitlabels: <a href="https://www.etsy.com/shop/8bitlabels?ref=simple-shop-header-name&listing_id=1097537372">8bitlabels on Etsy</a>

<b>Buying from RGRS? Consider helping out some cool people with these referral links:</b>
- <a href="https://retrogamerepairshop.com/?ref=ltyD2rUX">CodyWick</a>
- <a href="https://retrogamerepairshop.com/?ref=HSj4v5OO">JackV</a>

<b>Or use one of these other discount codes at checkout:</b>
- Nataliethenerd
- B23N
- Tito

### V. Battery Selection

I developed this system almost exclusively with rechargeable eneloop Pro NiMH AAA batteries. After finishing up development, I tried out regular alkaline AAAs. What I found, and some others have found, is that they are less reliable to use than NiMH batteries, particularly during start-up. When using alkaline batteries, after they have been discharged for an hour or two, sometimes the screen and power LED will flicker for a bit before fully coming on. This also varies between brands - I found Energizer Max batteries to perform much better than Duracell Coppertop batteries, for example. Duracells caused much more stuttering during the start-up sequence. Other brands or types may perform better, but I'm not about to buy a bunch of disposable alkalines to find out which.

However, the rechargeable NiMH AAA batteries I tested *do not* have any of these issues. And I tested these a lot during development, at many different states of charge. They are seemingly better suited for power delivery, and I never experience any kind of stuttering during start-up. I believe this is due to the generally higher internal resistance of alkaline batteries (a quick sampling of popular battery brands show approximately 50 mOhms internal resistance for NiMH chemistry, but 150+ mOhms internal resistance for alkaline chemistry). 

Rechargeable NiMH batteries give you about 3 to 6 hours of gameplay based on your settings and game selection, and as long as you have more than one set, you can easily charge one set while you play with another set. <A href="https://www.amazon.com/Panasonic-BK-4HCCA8BA-eneloop-Pre-Charged-Rechargeable/dp/B00JHKSL0A/ref=sr_1_1_pp?keywords=eneloop%2BAAA&qid=1690853200&sr=8-1&th=1">Here's a listing for the eneloop pro batteries I use in all of my Game Boys.</a> Other brands of rechargeable batteries I have seen used are Ikea LADDA batteries, and Jugee batteries.

#### Lithium Ion Batteries

Lithium-ion batteries (or LiPos) are another option, but I do not fully detail how to use them in this repository. You must be knowledgeable enough on your own to utilize them. Please review the entire repo for crucial information if you *do* decide to go with a LiPo.

I have created <a href="https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board">my own LiPo board</a> to fit in the U5 socket, but I really recommend using AAAs. It will make the assembly easier and safer.

Nataliethenerd's <a href="https://www.nataliethenerd.com/product-page/safer-charge-dc">Safer Charge DC</a> board is also compatible with the MGBC. Instructions for how to use it is in the Testing and Assembly section.
  
### VI. Compatibility with Other Mods

You don't need any extra mods to complete the MGBC build, but there are some options available. One of the goals for the MGBC was to provide compatibility with various mods by other makers. In general, I tried to make the board similar to the Game Boy Pocket PCB in terms of solder points for different kinds of mods. The MGBC will not benefit from any mods that include audio amplification/"cleaning" or tactile button mods, as I've included those improvements already. Check out the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/tree/main/MGBC%20PCB#customization-options">Customization Options</a> section in the MGBC PCB folder for information on those.
  
Here are a sample of my favorite mods for the MGBC:

  - <a href="https://www.etsy.com/listing/1267252807/game-boy-color-battery-indicator-mod">Leggomyfroggo's Two-Stage Battery Indicator Mod</a>: goes in place of the power LED, changes color when battery gets low
  - <a href="https://www.etsy.com/listing/1422095615/frogulator-game-boy-colorpocket-dc">Leggomyfroggo's Frogulator</a>: a power supply that slots into the U5 socket; eyes light up for battery power indication
  - <a href="https://www.muramasaentertainment.com/product/pocket-power-pocket/">Muramasa's Pocket-Power Pocket</a>: an all-in-one LiPo charger including USB-C port; requires some shell cuts and **removal of EM7 for v1.6 and earlier** [untested]
  - <a href="https://github.com/marshallh/gbpp">marshallh's Game Boy Pocket Power</a>: a power supply that slots into the U5 socket; has LiPo support (solder wires through the DC and BT+ holes on the MGBC board, and **remove EM7 on v1.6 and earlier** - requires USB-C board for charging and some shell cuts [untested]
  - <a href="https://github.com/skimzor/SZ-REG">skimzor's SZ Regulator</a>: a power supply that slots into the U5 socket; customizable print on the front of the board through <a href="https://ko-fi.com/skimzor">skimzor's Ko-Fi page</a>
  - <a href="https://www.nataliethenerd.com/product-page/gbp-led-boards">Natalie the Nerd's LED Boards</a>: button LED backlight board

Important note for using external mods: you must be aware that the voltage on the SW net (the output of the power switch, connected to pin 1 on the power board socket) will remain connected to the batteries as long as the power switch is on. If your mod connects to the power switch output, then be aware there *will* be a condition where the 5 V on-board is at zero volts, and the battery voltage will still be above 2 V. This may cause issues, such as power draw through resistors even when the power is off, or leakage through protection diodes in certain devices. Please use accordingly.

## Testing and Assembly

I'm going to split this into a few separate sections. This is the general process I follow when assembling an MGBC.

### Circuit Board Assembly

Usually when I'm populating a board, I follow this order:
  
1) Assemble all the non-Gameboy surface mount components first, not including P2, U2, C24, C29, and C45. 
  
2) After soldering these components, I solder the CPU and RAM in, then the FFC connector.
  
3) I use hot air and solder paste to reflow X1, C24, C29, and C45 onto the board. Be sure to either cover the FFC connector with kapton tape to avoid melting the plastic, or heat the board from the bottom.
 
If the build is going to utilize tactile buttons (the ones that are clicky, like on the GBA SP) I install *at least* the start and select ones now. After the headphone jack and DC jack are in, it's tricky to get the start and select tactiles in.
  
4) Finally, I add most of the other external-facing components - VR1, P3, P4, P5, SW1, SW2, D2, the speaker, and the battery terminals. The only parts that I don't populate at this point are the cartridge connector (P1) and the power board (U5). 
  
![assemblysteps](https://user-images.githubusercontent.com/97127539/235049911-c1a1544d-e6bf-4002-8d76-e58140b73a33.png)

**NOTE 1** - Keep VR1 and SW2 as far inside the board as the holes allow. This will reduce interference with the shell. You may need to file away a bit of the shell in order for the knobs to turn freely. It may be a good idea to do a quick fitment test in the shell before going farther into assembly.

**NOTE 2** - You may have to trim the pins on VR1, the volume dial, before soldering. I cut them down in half to make them fit nicer.

![image](https://user-images.githubusercontent.com/97127539/235283222-67c8e9a2-00a4-41b4-9448-10cceecbf2e5.png)
  
### Setting up for AAA vs LiPo

I generally recommend using NiMH AAAs in builds, because they are easier and safer to deal with, they can be swapped in quickly as opposed to waiting for the battery to charge up, and don't require any shell modifications to use (LiPos require a shell cut to fit a USB port, which isn't fun). The only thing you need to do if you're going to use AAAs, which the MGBC is set up for natively, is connect the two holes labelled BT+ and DC together with a wire or 0 ohm resistor. This is also only required on v2.0 and later boards - v1.6 and earlier do not require this. Shorting these holes together connects the DC jack to the input of the regulator. So if you forget to add it, then your DC jack won't work (which may or may not matter to you anyway). **DO NOT SHORT THESE TOGETHER IF USING A LITHIUM-ION BATTERY.**

![image](https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/assets/97127539/f868dfd0-655a-4517-a6ca-ef92e4695432)

If you really want to add LiPo support to your build, you're on your own for figuring out how to set it up. The important thing to note on the MGBC board is, for boards v1.6 and earlier, **DO NOT INCLDE EM7**. This component must be removed from the final build. Make absolutely sure you do this - failure to do so may damage your battery and/or system. In version 2.0, you must include EM7 on every build.
  
![image](https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/assets/97127539/7d463a96-67b7-4514-8e9a-4d1b59431016)

Also, to get the power LED to dim at the correct time, remove R6 from the main MGBC board.

![image](https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/assets/97127539/850de545-a5db-4b9c-8bde-c738271bcfe5)

If you're using Nataliethenerd's <a href="https://www.nataliethenerd.com/product-page/safer-charge-dc">Safer Charge DC</a>, connect a wire from the "To F1" pad on the back of the board to the BT+ hole on the MGBC, and a wire from the "To 5V" pad on the back of the board to the pad on the USB-C breakout board. Then install the board into the U5 socket as normal.

![image](https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/assets/97127539/469336df-84e2-4dd5-8900-eac6d3844ded)

And, as a mandatory disclaimer, **LITHIUM-ION BATTERIES ARE DANGEROUS. USE AT YOUR OWN RISK. I AM NOT RESPONSIBLE FOR YOUR HOUSE BURNING DOWN. YOU ARE RESPONSIBLE FOR FIGURING OUT HOW TO USE A LIPO ON THIS BOARD.**

### Testing the Power Board and IPS Kit
  
The next step to test is the power board, or U5. If you are using my LiPo power board, the steps to test that board are detailed <a href="https://github.com/MouseBiteLabs/Pocket-Protector-Power-Board">in the repository.</a> I *highly* suggest making sure you've assembled the power board correctly before directly connecting it and powering it all on, cowboy style. If you're able to test your power board before installation, definitely do that, but if you're not sure how, or don't have the ability, then you can actually use your mostly-assembled MGBC board to test it. 
  
Solder wires on pins 1, 2, and 3 from the MGBC board to the power board (the left three holes of the power board). Don't connect the other side of four pins just yet - pin 7 is the 5 V pin, which powers the rest of the Game Boy. Keeping pin 7 depopulated, you can place the Game Boy in the back half of the shell to connect up batteries, or use a power supply clipped to the battery terminals. Turn the power switch on. Use a multimeter to measure the voltage from pin 7 (positive test probe) to GND (negative test probe). You should read approximately 5 V here - anything more than 5.1 V or less than 4.9 V means you've likely got something wrong on your power board.
  
(In this picture, the red circle is pin 7, the blue circle is pin 3, or GND - this is for illustrative purposes only, I recommend testing the board before fully mounting it to the MGBC board.)
  
![image](https://user-images.githubusercontent.com/97127539/235282279-d22b57a9-9a5a-4d9a-9d33-f8fa2a7b4e75.png)

If you confirm you have 5 V on pin 7, then remove the wires and connect the board via header pins (if not, check the next section for some troubleshooting advice). Finally, you'll want to test the screen kit. Slide the FFC cable into P2 on the MGBC board, and make sure the cable is all the way in and the bale is pushed all the way down. Let the screen hang over the front of the board. I recommend placing something insulative - like a piece of paper, or kapton tape - over the empty holes of the cart connector, to prevent the back of the display from shorting on the pins. If you have a power supply, you can use that to power it on the battery terminals (set it for 3 V, 1.5 A). If not, you can again put the Game Boy in the back half of a Game Boy Pocket shell to use batteries. (I have mixed results with using battery holders with alligator clips.)
  
![image](https://user-images.githubusercontent.com/97127539/235283500-ccf2f536-ea98-42ce-b0f8-d0a40bca9275.png)
  
Turn it on, and check for these things:
  
1) Power LED turns on
2) The speaker makes the start-up ding (use headphones to check both left and right channels, and check the volume)
3) The screen shows the GBC splash logo
  
Some quick troubleshooting tips - first, make sure the batteries are in all the way (or your power supply is set correctly) and the cable for the IPS kit is inserted fully and the bale is pushed all the way down. If only the LED isn't turning on, you might have the LED backwards. If you can hear the start-up noise, but nothing on the screen, then check the connections on the FFC connector and the top row of pins on the CPU - they probably need a reflow. If you get a blank screen, but no start-up jingle, then check the connections on the FFC, CPU, and RAM chips. And if you have the splash screen, but no audio, then check your speaker, headphone jack, and orientation of tantalum capacitors. If nothing is happening when you flip the switch, or you still cant figure out where your error is coming from, check out the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color#troubleshooting-common-electrical-issues">Troubleshooting</a> section for a few more detailed troubleshooting tips, and the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/tree/main/MGBC%20PCB#cpu-pin-functions">CPU Pin Function diagram</a> in the PCB folder.

*Note: If you're using the Pocket Mouse Power Board, you may have to wait a few seconds after inserting batteries the first time before it will turn on with the power switch. Once the batteries have been in the system for a few seconds, it will act completely normally.*
  
Once you've verified the system boots up correctly, and you have acceptable sound coming out of the speakers and headphones with the start-up noise, you can go ahead and put the cart connector into the board. I save this for last, because there are a few components in the audio circuit close to the connector, and they're difficult to rework without melting the cart connector plastic.
  
When you install the cartridge connector, be sure to trim down the pins nearly flush to the PCB. Then, I usually cover the exposed solder with kapton tape. The Q5 screen sits right above these pins, and the back of it can short to the cart connector pins once the system is fully assembled.
  
![image](https://user-images.githubusercontent.com/97127539/235283082-a844ecf2-d0d5-4473-99e0-92a3c2a186fa.png)

You will also want to test out the cartridge connector! Put the screen back in, and power it up like you tested above, but with a game inserted this time. If you get a garbled Nintendo logo, or the game doesn't boot at all, make sure your cartridge and cartridge connector are cleaned. You may also want to reflow the cart connector or the bottom row of CPU pins in case one of those lines are not making proper connection.

I suggest running the color tests in the <a href="https://github.com/pinobatch/240p-test-mini/releases/">240p test suite ROM</a>, if you have a flash cart to run it on. It will tell you if you have any poor connections on the FFC lines - the screen might work, but you might be missing a connection on one of the 15 RGB pins! If your colors look off, reflow the connections on the top row of pins on the CPU and/or the FFC connector. This picture (provided by <a href="https://retrogamerepairshop.com/?ref=HSj4v5OO">JackV</a>) shows a before and after pic for reflowing a few mis-soldered color pins.

![image](https://user-images.githubusercontent.com/97127539/235316239-43251055-ed33-4d0a-b5b8-bf5c3a8b2e9e.png)

### Customization Options

There are a number of options you have to customize your build. This includes, among other things: adding a reset button, adding tactile switches for the buttons, and changing the brightness of the LED. Review the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/tree/main/MGBC%20PCB#customization-options">Customization Options</a> section of the MGBC PCB folder for more information.

This is also the point where I would install any desired mods discussed above in the <a href="https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color#v-compatibility-with-other-mods">Mod Compatibility</a> section (other than power boards, obviously). Though, there aren't too many mods out there that would be required to add. Again, there is absolutely no need for additional audio mods or power cleaner mods on this build.

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
  - Clean your power switch regardless of any issues (it will improve the switch action reliability), but if it's particularly dirty, you may not get any voltage reading on pin 1 even when it's turned on
  
**Issue: Severe power glitches during start-up; plugging in headphones sometimes resets system**
  
  - Make sure C8, C21, C26, and C27 are placed in the correct orientation. Remember, the stripe on tantalum capacitors indicates the POSITIVE side of the device.
  - Ensure R22/R23 are 1 kΩ resistors.
  - Clean your power switch properly.
  
**Issue: No sound or bad quality sound**

- Make sure C8, C21, C26, and C27 are placed in the correct orientation.
- Plug in headphones to check if the issue is related to the speaker or both speaker and headphones. If you get audio out of your headphones but not your speaker, then:
  - Check for continuity from pin 5 on the headphone jack (top right corner when viewing from below) to GND. When headphones are not plugged in, this pin should be connected to ground. If it isn't, clean your headphone jack, or get another.
  - Try another speaker, if you have one.
- If your issue is both speaker *AND* headphones, then:
  - Clean your volume dial by dripping IPA in it and spinning it back and forth. Consider replacing it with a new aftermarket version.
  - Reflow components in the audio circuit and/or the CPU audio pins.
  
**Issue: White screen, glitchy display, miscolored display, stuck on the boot logo**

- Make sure your screen ribbon cable is inserted all the way into P2 and the bale is pushed all the way down.
- Reflow the SRAM (U2) and make sure all pins are well-connected to the board.
- Reflow the FFC connector (P2) and make sure all pins are well-connected to the board.
- Reflow the CPU (U1) and make sure all pins are well-connected to the board.
- If miscolored, make sure the palette isn't being cycled on the IPS kit, as there is a touchpad that cycles through different color modes.
- If you're stuck on the boot screen *only* with a game inserted, check to make sure the cartridge and cartridge connector you're using is clean and making good contact.

### Final Assembly

Before assembling the board into the shell, it's a good idea to prepare the Q5 board solder pads. First, remove the touch sensor leads. Then cut six 30 gauge wire segments and solder them on the brightness, palette, battery, and OSD input pads. You do not need to solder a wire to the GND pad. The one connected to the brightness touch sensor pad will be longer than the others, as it has to cut over to the other side of the board. These wires will be soldered to the top of the board after the screen is installed.

Then, put the lens on the front half of the shell, take the screen protector off of the IPS screen, and carefully place it in the back half of the shell - be sure no dust or hair is between the lens and the screen! Then place the buttons and membranes down.

![image](https://user-images.githubusercontent.com/97127539/235335579-8f236275-aaf2-4186-ab9b-87b1cbd5b1b0.png)

**Note: Be extremely careful with the screen. It is fragile. If you break it, you can sometimes buy one separately. They're just screens that were used in Blackberry Q5 phones.**
  
Next is to put the assembled PCB into the shell. Remember that you may need to lightly file away part of the shell around VR1 (volume dial) and/or SW2 (rocker switch) if the knobs interfere with the shell. Put screws down into the proper holes, and feed the IPS kit cable into P2 and secure the bale. The cable is a bit stiff so be careful installing it. Also at this point, *very carefully* solder the six wires from the IPS kit onto the main MGBC PCB. **Be extremely cautious not to melt any plastic on the shell!** Though if you're attempting this mod, I would hope you have a steady enough hand to keep the soldering iron away from the melty bits ;)

![image](https://user-images.githubusercontent.com/97127539/235335793-c553a47c-2323-4034-8f37-74512b3923cf.png)

Then all that's left is to put the power switch in its holder, and secure the back half of the shell on. Well, and center the image. It's going to be offset a bit. That's where the Q5 kit's image-centering functionality comes into play. Open the menu by pressing Select, A, and B at the same time. Navigate up and down in the menu with A and B respectively, and hold select and press A to select the screen offset options (select+A again confirms your change, select+B backs out of it). Adjust the V (and maybe H) coordinates so that the image is centered, for my build this was about 46 vertical, 37 horizontal.

*Also, if your screen kit includes the option for a backlit Game Boy Color lens logo, be sure to disable that in the OSD menu. On the left picture you can see the blue bar at the bottom, that's the backlit logo option before disabling it.*

![image](https://user-images.githubusercontent.com/97127539/235335829-75f2d6c4-7cbb-4763-a4be-219cd9685b27.png)

Add any stickers you want, and the MGBC is complete!

![image](https://user-images.githubusercontent.com/97127539/235335874-ff820049-6666-4099-8ad0-025da20a4e00.png)

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
For these estimates, battery life was measured using two eneloop pro NiMH AAA batteries (total of ~2232 mWh) while playing the Legend of Zelda: Link's Awakening intro on loop. Keep in mind, these are rough estimates. I rounded to the nearest 5 minute interval, and the nearest 5 mW interval. Actual playtime *will* vary due to a variety of factors, but these should be good ballpark numbers. 

In general, you can expect to get between 3 and 6 hours of gameplay depending on the game, your play settings, and the batteries you're using. The power LED will dim with about 10 to 20 minutes left of playtime.

| IPS Screen Brightness | Cartridge Type | Volume | Headphones? | Playtime       | Power Draw (mW) |
| --------------------- | -------------- | ------ | ----------- | -------------- | --------------- |
| Max                   | Everdrive X5   | Max    | No          | 3 hrs, 15 mins | 680             |
| Max                   | Everdrive X5   | Max    | Yes         | 3 hrs, 30 mins | 635             |
| Max                   | Everdrive X5   | Min    | N/A         | 3 hrs, 30 mins | 630             |
| Max                   | OEM Cart       | Max    | No          | 3 hrs, 30 mins | 630             |
| Max                   | OEM Cart       | Max    | Yes         | 3 hrs, 45 mins | 590             |
| Max                   | OEM Cart       | Min    | N/A         | 3 hrs, 50 mins | 585             |
| Min                   | Everdrive X5   | Max    | No          | 4 hrs, 25 mins | 500             |
| Min                   | Everdrive X5   | Max    | Yes         | 4 hrs, 45 mins | 465             |
| Min                   | Everdrive X5   | Min    | N/A         | 4 hrs, 50 mins | 460             |
| Min                   | OEM Cart       | Max    | No          | 4 hrs, 50 mins | 460             |
| Min                   | OEM Cart       | Max    | Yes         | 5 hrs, 20 mins | 420             |
| Min                   | OEM Cart       | Min    | N/A         | 5 hrs, 25 mins | 415             |

The variable that affects battery life the most is the screen brightness. I have found that the power drop from full to half brightness is much larger than the drop from half to minimum brightness, so I recommend playing at half brightness to maximize playtime without sacrificing a vibrant screen. As for cart type, I only own an Everdrive X5, which of the flash cart offerings is one of the most power efficient. So something like the EZ Flash Jr. is likely to drain batteries even faster. 

The difference in power draw between max and min screen brightness is about 170 mW, between an OEM cart and an Everdrive X5 is about 45 mW, between max and min volume on speakers is about 45 mW, and between headphones and speakers is about 40 mW.

### Battery Discharge Curves

These are six curves generated from data used to populate the table above, with the x-axis being depth of discharge.

![image](https://github.com/MouseBiteLabs/Game-Boy-Pocket-Color/assets/97127539/691c74dd-b451-4a08-8384-6c45a36ec084)

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
  
Please refer to this before asking me any questions! If you ask me a question, I'm going to automatically ask you if you read the FAQ and this entire repo first.
  
**Q: Can you make one for me?**
  
A: NO. Stop asking, please! There are makers out there who you can commission a build from, but I am not one of them.
  
**Q: Why are you encouraging the destruction of Game Boys?**
  
A: If you can properly complete this mod, you will have destroyed net-zero Game Boys, as you get a working Game Boy when you finish. It's also a great way to rehabilitate an otherwise damaged Game Boy, as you only need a few working parts to construct an entirely new working one. Let's refurbish those damaged Game Boys!
  
**Q: Aren't you contributing to the rising prices of Game Boys by doing this?**
  
A: <a href="https://en.wikipedia.org/wiki/Game_Boy_Color#:~:text=The%20Game%20Boy%20and%20Game,game%20console%20of%20all%20time.">There were over 100,000,000 Game Boy Colors sold around the world.</a> So, no, not in any appreciable manner.

**Q: My EM10 has an extra leg in-between two of the other ones. Can I use this part?**

A: Yes, just bend up the extra pin so that it doesn't contact any of the nearby pads. It is an unused anchor pin.

**Q: Sometimes the power switch is finnicky and the system won't power on consistently. Sometimes the IPS screen will turn on, but only the backlight, not the actual image. What gives?**

A: <a href="https://www.youtube.com/watch?v=2_Pt_odHyzo">Clean your power switch.</a> This fixes most issues. Do it properly - if you're attempting this mod, you should be able to properly clean your power switch.

**Q: I'm using a battery holder with alligator clips to test the system, and it's not turning on. Why?**
  
A: I've found that sometimes the contact resistance from the alligator clips was enough to prevent the system from powering up properly. Try putting the board in the shell and inserting the batteries in the back normally.
  
**Q: Can you make a [brand new Game Boy circuit board that combines x and y]?**
  
A: I dunno man, maybe, but I don't want to right now. Can I go to sleep yet?
  
## Acknowledgements

- <a href="https://github.com/MouseBiteLabs/Game-Boy-DMG-Color#acknowledgements">Thanks to everyone I already thanked for the technical support and resources for my DMGC project,</a> as most of the work I did on that was directly applicable to this one.
- VERY special thanks to all the alpha and beta testers who took time and money to build boards and give me extremely useful feedback on the design. You made the final product better than I could have done on my own.
- Thanks to the awesome members of the <a href="https://moddedgameboy.club/">Modded Gameboy Club</a> for their feedback and support during the entire project development.
- Thank you to skimzor for support on the initial layout, providing me with reference measurements for all the external components, like the power switch and volume wheel. <a href="https://github.com/skimzor/SZ-POCO">Check out his own Pocket Color boards!</a>
-	Of course, huge thank you to everyone who has <a href="https://ko-fi.com/bucketmouse">donated and supported me</a>, and to those who have built their own MGBC! I love seeing pictures of builds, so feel free to share them with me on Twitter, <a href="https://discord.gg/Y5aDvCcpbX">discord</a>, or via email!

## License
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>. You are able to copy and redistribute the material in any medium or format, as well as remix, transform, or build upon the material for any purpose (even commercial) - but you **must** give appropriate credit, provide a link to the license, and indicate if any changes were made.

This project is the culmination of over a full year of research, development, and testing. I have made this project completely open-source, and have put hundreds of hours of work (and dollars!) into it, so that many people can enjoy it. **Please** give me appropriate credit where credit is due.

©MouseBiteLabs 2023
