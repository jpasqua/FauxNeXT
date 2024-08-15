# Building the FauxNeXT
These instructions are a work-in-progress. As problems are noted or suggestions arise, I will update the instructions. Thank you for your patience. Throughout the Instructions when I am referring to a printed part, I will italicize the name. For example: *MainLeg*. As of this writing (August 2024), these instructions are only for the [NeXT MegaPixel Display](https://en.wikipedia.org/wiki/NeXT_MegaPixel_Display) (MPD). In the future other models may be added such as a [NeXTstation](https://en.wikipedia.org/wiki/NeXTstation) and/or a NeXT Sound Box.

Below are some reference images of the assembled model. 

[<img src="images/Actual/Faux_and_Real_3.jpeg" height="256">](images/Actual/Faux_and_Real_3.jpeg)
[<img src="images/Actual/Full_Portrait_Kbd_2.jpeg" height ="256">](images/Actual/Full_Portrait_Kbd_2.jpeg)
[<img src="images/Actual/Faux_and_Real_Back.jpeg" height ="256">](images/Actual/Faux_and_Real_Back.jpeg)

[<img src="images/Model/Full_Front.jpeg" height ="256">](images/Model/Full_Front.jpeg)
[<img src="images/Model/Full_Back.jpeg" height ="256">](images/Model/Full_Back.jpeg) 

## Required Supplies

### Required Electronics (and where to source)

* **Raspberry Pi 4/5**. I tried both a model 4 and a model 5. I ended up using a Pi 5, but the Pi 4 is adequate. There are many places to source these. To find one you can use [rpilocator](https://rpilocator.com/).
* **Power Supply**. You will need a hefty USB-C power supply for this since it is powering the Pi itself, the display, and any attached USB peripherals like USB speakers. You don't want to skimp here. If you do, you are likely to get "Low Voltage" warnings from the Pi. For a Pi 4, the [CanaKit Pi 4 Power Supply](https://www.amazon.com/gp/product/B07TYQRXTK) has worked for me, though  For a Pi 5 I have had success with a [GeeekPi 27W Power Supply](https://www.amazon.com/gp/product/B0CQ2DL2RW). I'm sure there are many others that will work, but what won't work is an old phone charger with a random USB cable.
* **8" 1024x768 Display**. The MPD has an odd display resolution. The 17" monitor had 1120 × 832 pixels at 92 DPI. This is 4x3 aspect ratio so I chose a similar size and shape: 1024x768. As the model is 50% scale, I used an 8" display. I had to modify the bezel a bot to accomodate this. I got my display and controller card on [ebay](https://www.ebay.com/itm/163726876776).
* **Keyboard**. There were a couple of different models of NeXT keyboard. I didn't recreate any of them. At this point, just use a small USB or bluetooth keyboard (and mouse) of your choosing,
* **HDMI Cable**: The display connects to the Raspberry Pi via HDMI, but there is not a lot of room for bulky HDMI cables. I used a flat-flex cable with an up-angle HDMI connector for the display and a micro-HDMI connector for the put. I used [this cable](https://www.amazon.com/JSER-Degree-Angled-Multicopter-Photography/dp/B072PVG4B4), but others are available that will fit. You can mix and match ends or buy a cable with both ends supplied (check the supplier's Amazon store).
* **Power switch**. The Pi 5 accomodates a soft power switch. You'll need a standard momentary push button. I used one which I had "in stock", but any 12mm switch will do, such as [this one](https://www.amazon.com/Momentary-Waterproof-Pushbutton-Pre-Wired-Automotive/dp/B0C8HLLGYG) on Amazon. If you use a Pi 4, a soft power switch is not supported.
* **Boost Converter**. The display runs on 12V, so you'll need to boost the 5V supply coming in. There are lots of available boost converters. The *Display_Retainer* has mounting spots for [this one](https://www.amazon.com/gp/product/B0833SQF8Z).
* **Wires**
	* **Bits of Wire**. You'll need a few bits of wire to connect the Pi 5 to the soft power switch, the Boost Converter to power out from the Pi, and the display to the Boost converter.
	* **Wired Connectors**. To make FauxNeXT easier to assemble/dis-assemble you may wish to use [wires with connectors](https://www.amazon.com/gp/product/B0CKYNMGHL) between various components. You can see where I used connectors in the [images of the wiring](#WiringImages).

### Required Hardware

# JP: Pick up here.

You will need an assortment of screws to assemble the model:

* (2) M3x6 cap head screws for the USB-C breakout board
* (2) M3x4 cap head screws for the Boost Converter
* (4) M2x4 cap head screws to attach the Raspberry Pi to the *Main Case*.
* (4) M3x4 cap head screws to attach the display board to the *Display Retainer*
* (4) M3x6 cap head screws to attach the *Display Retainer* to the *Front*
* (8) 6mm round magents (3mm deep) to attach the *Front* to the *Main Case*

Refer to the [reference images](#HardwarePlacement) in the Assembly section for placement.

### Filament

I used PLA for all components, but for no other reason than it is what I normally use and my models won't be in an environment where the properties of other filaments will be required. If this turns out to be untrue, I will update this note.

* **Beige Filament**:
	* The *Main Case*, *Front*, and *Keyboard Shell* should be printed in a beige-ish Filament to match the Macintosh. My most recent print used [Polymaker Matte PLA "Muted White"](https://www.amazon.com/gp/product/B09TR8N5T2). I'm interested in other suggestions for filaments that match the Macintosh better. Another option is to print the model in a neutral white and spray paint it with a matching paint.
	* The *Display Retainer* can be printed in any color, so if you have the beige loaded in your printer, you can just use that.

### Other
* **CA Glue**: A small amout of CA glue is needed to attach magnets to the *Front* and the *Main Case*.
* **Patience**: This can go a long way towards a successful build.

## Printing the Parts

Printing and assembling this model will take some time. The largest part, the *Main Case*, requires supports and takes me about 6 hours to print on a BambuLab X1. All of the STLs will import into your slicer in the orientation in which I printed them. STLs that need supports have “(NS)” in the name. I used tree supports and removing them was fairly easy. All parts may be printed with a 0.2mm layer height.

* ***Main Case (NS).stl***. This is the largest single print and, as the name shows, it requires supportsfor the handle area. Your slicer may recommend tiny supports at two of the bottom corners. it is up to your printer whether they are really required.
* ***Face (NS).stl***. This component requires supports for the display opening. Your slicer may want to add supports for the magnet recesses. I don't find them to be necessary so you can suppress supports in those four areas.
* ***Display Retainer (NS).stl***. This part screws into the *Face* to hold the display in place. It also provides a spot to mount the controller board for the display. It requires supports, but they are minimal and easy to remove.
* ***Keyboard Shell (NS).stl***. This standalone component houses the small wireless keyboard. It is listed as requiring supports, though technically it doesn't if printed in it's natural orientation. I print it on end to avoid stair-step ridges in the top of the shell. You can re-orient it to avoid supports if you prefer.

## Assembly

After printing the parts, removing supports, and doing any other cleanup/post-processing that you deem necessary, you are ready to assemble the model. The steps below are for the physical assembly, but you'll need to do the wiring along the way. An overview of the wiring is given in a separate section, but is called out in the steps below. 

All of the screws mount directly into the plastic of the model. You may want to run some screws into the holes a bit to make it easier to start the screws during the actual assembly process. Do no over-tighten.

1. Using a small dab of CA glue, affix a magnet into each corner of the *Main Case*. You will notice that the bottom two magents are slightly recessed (about 1mm). To establish the proper orientation for the four remaining magnets, stick them magnetically to the glued magnets. Make a mark on the visible face of these magnets. The mark should indicate which corner that magnet goes in, and its orientation. For example, you might write "LL" on the magnet that goes in the lower left corner.
1. Using a small dab of CA glue, affix one of the marked magnets into each corner of the *Face*. The marked face of the magnet goes into the recess. It is critical to get the orientation right, so double-check before gluing.
2. ***Perform wiring as [described below](#Wiring)***
1. Very carefully thread the flat-flex cable from the display through the *Display Retainer* and connect it to the connector on the display board. It is very easy to rip this cable and extremely hard to fix it. [See this photo](images/Assembly/Assemble_Display_1.jpeg) proper orientation.
  * **NOTE**: At this point you should have soldered wires to the back of the display board if you are not going to use the barrel connector.
1. Screw the display board to the back of the retainer as [shown here](images/Assembly/Assemble_Display_2.jpeg).
1. Peel off the clear protective plastic from the front of the display, then attach the display, display board, and *Display Retainer* to the back of the *Face* using four screws.
1. Install the Raspberry Pi using four M2 screws.
2. Install the power switch
1. Secure the USB C breakout board using two M3 screws
1. Secure the Boost Converter using two M3 screws
1. After testing the unit, snap the *Front* to the *Main Case*. the magnets will hold it in place.
2. I put a small self-adhering rubber foot at each corner of the bottom of the *Main Case* to make it less likely to slide. This is completely optional. I used some feet I happened to have lying around, so I'm not sure exactly what they are. They look like [these](https://www.amazon.com/Adhesive-Drawers-Furniture-Dampening-Transparent/dp/B08NX9KXQP).
2. Have a break then move on to Software Setup.

<a name="HardwarePlacement"></a>**Hardware Placement**:

[<img src="images/Assembly/HW/Magnets_Face.jpeg" height ="256">](images/Assembly/HW/Magnets_Face.jpeg)
[<img src="images/Assembly/HW/Magnets_Main_Case.jpeg" height ="256">](images/Assembly/HW/Magnets_Main_Case.jpeg)
[<img src="images/Assembly/HW/Face_Screws.jpeg" width="256">](images/Assembly/HW/FaceScrews.jpeg)
[<img src="images/Assembly/HW/Main_Case_Screws.jpeg" width="256">](images/Assembly/HW/Main_Case_Screws.jpeg)

<a name="Wiring"></a>
## Wiring

The wiring is fairly simple. You can see most of it in the photos. I will trace through the connections starting with the USB-C connector. Depending on how much you want to facilitate disassembly and changes, you may wish to use two prong connectors at certain spots. Refer to the images to see where I used connectors.

1. Connect `VBUS` on the USB breakout board to one leg of the power switch.
1. Connect the other leg of the power with to the positive (red) leg of the USB Cable End.
1. Also connect the same leg of the power switch to `IN+` on the Boost converter.
1. Connect `GND` on the USB breakout board to `IN-` on the Boost converter.
1. Also Connect `GND` on the USB breakout board to to the ground (usually black or white) leg of the USB Cable End.
1. Output from the Boost Converter. You have a couple of options here:
    2. Connect the outputs of the boost converter (`OUT+` and `OUT-`) to a cable with a male barrel connector on the end. It should correspond to the female barrel connector on the display. Plug in the barrel connector.
    3. *Alternatively*, solder a red wire and a black wire to the back of the display board. If you look at the board near the barrel jack you'll see pads labeled `12V` and `GND`. You can use those or solder directly to the  legs of the barrel connector. If you use this method, it is convent to put some type of 2-pin connector between the Boost converter and display so they can be separated easily. This is the approach I took. See the reference photo.
    4. **Important**: Adjust the Boost Converter output to 12V. If the voltage is too high, it may damage your controller board.
1. Connect the angled HDMI connector to the input of the display board.
1. Connect the free end of the HDMI cable to the Raspberry Pi.
1. Plug the USB Cable End into the Raspberry Pi.

<a name="WiringImages"></a>**Reference images**:

[<img src="images/Wiring/Wiring_Case_1.jpeg" height="256">](images/Wiring/Wiring_Case_1.jpeg)
[<img src="images/Wiring/Wiring_Case_3.jpeg" height="256">](images/Wiring/Wiring_Case_3.jpeg)
[<img src="images/Wiring/Wiring_Full_1.jpeg" height="256">](images/Wiring/Wiring_Full_1.jpeg)
[<img src="images/Wiring/Display_Board_Power.jpeg" height="256">](images/Wiring/Display_Board_Power.jpeg)
[<img src="images/Wiring/HDMI_Cable.jpeg" width="256">](images/Wiring/HDMI_Cable.jpeg)

## Software Setup

* **Prepare Raspberry Pi OS**. Create an image of the Raspberry Pi OS that is appropriate for your Pi. Don't use the Lite version - you'll need the window system installed. I used the latest OS release as of July 2024, Bookworm. Boot the OS.
* **Adjust Screen Settings**: The display board comes with a control board with several buttons. The boards are connected to one another through a fairly flat 6-wire cable. You won't be using the control board in normal operation, but you may wish to connect it during initial setup to adjust things like input source, brightness, etc. After that you can remove the control board and cable and only reattach it if needed.
* **Flip the display orientation**. Because of the placement of ports on the display, it must be mounted upside down in the case. This means that the display orientation needs to be flipped 180&deg;. This is accomplished using the Screen Preferences in the Raspberry Pi desktop. Selected the inverted option.

	[<img src="images/SW/ScrPrefs.png" width="256">](images/SW/ScrPrefs.png)
	[<img src="images/SW/Inverted.png" width="256">](images/SW/Inverted.png)

  Once you've done this, the Window System will display properly. Note, however, that as the Pi is booting, everything will appear upside down until the window system launches.
* **Build the Mac emulator: Basilisk II**. Please refer to the instructions on [GitHub](https://github.com/kanjitalk755/macemu) to learn how to build Basilisk II. I have included my general process below, but you should always use the newest instructions from GitHub. The build instructions boil down to entering these commands into the shell:

		```
		cd ~
		# Get the required dependencies
		sudo apt install git libsdl2* automake samba samba-common smbclient libmpc-dev -y
		# Get the emulator
		git clone https://github.com/kanjitalk755/macemu.git
		# Perform the build
		cd macemu/BasiliskII/src/Unix
		./autogen.sh
		sudo make install
		```
* **Get a ROM file**: The emulator needs a copy of a ROM image from an old Mac. You can download it using the command below and place it in the `~/emulator_resources` directory:
	
		```
		cd ~/emulator_resources
		# Get the ROM file
		wget https://raw.githubusercontent.com/ekbann/chromebook-basilisk2-sdl2/main/Quadra800.ROM
		```
* **Create a Basilisk prefs file**. This file points to your ROM file and your disk image. It also specifies a directory on your Pi which will appear as a shared disk on your virtual Mac desktop. If you want the emulator to start full screen, use the file as-is. If you'd like to start in a window, comment out `screen dga/512/342` by adding a `#` at the beginning. Uncomment the other `screen` line by removing the `#`.
Here is how I create mine:

	   ```
		mkdir ~/.config/
		mkdir ~/.config/BasiliskII
		echo "rom /home/pi/emulator_resources/Quadra800.ROM
		disk /home/pi/emulator_resources/System7.5.5.dsk
		ramsize 142606336
		# ether slirp
		nocdrom true
		extfs /home/pi/emulator_resources/shared
		frameskip 0
		modelid 14
		cpu 4
		fpu true
		#screen win/512/342/1
		screen dga/512/342
		displaycolordepth 8" > ~/.config/BasiliskII/prefs
	   ```
* **Create/Obtain a Mac Disk Image**: This is the trickiest part of the emulator setup process and I won't repeat all the details here. I supply an image as part of this repository, but it is not allowed. Please refer to [these instructions](https://www.emaculation.com/doku.php/sheepshaver_basiliskii_linux). You may find it easiest to run Basilisk on a Mac or Windows machine and create the image there. Then you can just copy it to your FauxNeXT and place it in the `~/emulator_resources` directory. As you can see in the `prefs` file mentioned above, my disk image is in a file named `System7.5.5.dsk`.

