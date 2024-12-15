# Peopoly Magneto X Frequently Asked Questions

###### Last Updated: 12/16/24

All questions pertain to printer shipping version of 10/1/24 or later unless otherwise specified.

Where authors provided it only reflects who wrote the FAQ section as all answers have many community contributions.

Please send any questions, comments, suggestion, new FAQs to @kaihanga on Discord or via kaihanga@nulleta.com

# General
- [What's the size, measurements, etc.?](#whats-the-size-measurements-etc)

# Printer
- [How to install a Beacon?](#how-to-install-a-beacon)
- [How to SSH into the printer?](#how-to-ssh-into-the-printer)

# Enclosure
- [How to install Display at top?](#how-to-install-display-at-top)

# Support & Community
- [Is there a community to share and learn about other's experience?](#is-there-a-community-to-share-and-learn-about-others-experiences)

# Other Section Ideas
### Filament
### Printing (common VFA, Ringing suggestions, etc.)

# Answers... ish
<a name="whats-the-size-measurements-etc"></a>
## What's the size, measurements, etc.?

###### Author(s): @kaihanga

**Bed**: 400mm x 300mm x 300mm

**Printer**: 60.5cm x 54cm x 71cm (length, width, height)
- Add 26cm on right side (printer facing you) for filament spool & power cable
- Measurements includes slack for filament feed line

**Enclosure**: add 4.5cm to height and 25cm for front door access   

<a name="how-to-install-a-beacon"></a>
## How to install a Beacon

> [!CAUTION]
> In progress, don't follow

###### Author(s): @kaihanga

Notes:
- Order Beacon Normal, not low-profile, and 10' cable
- You'll need to be comfortable with SSH access and Klipper UI navigation

1. Print mount, I used [this mod](https://discord.com/channels/1158578009121501267/1286448210868437023) in ASA-CF
	1. It's going to be near bedheat so heat deflection, etc. is good
	2. Included PETG-CF isn't enough, reports of sagging
	3. Must be stable
2. Using linked mount
   1. unscrew 4 screws near nozzle
   2. Slightly move nozzle cable out of way and return when done, 2 are clockwise while two are counter-clockwise
   3. Attache Beacon with pointed side facing the nozzle 
   4. Hand-tighten
3. Attach cable connection to beacon, tab facing nozzle
4. Unscrew bottom right side base cover, 10 screws
5. Attach USB cable to any USB port
   1. Be sure there's plenty of slack and the cable's not interferring with the toolhead  
6. Power on printer
7. [Follow Beacon Quickstart](https://docs.beacon3d.com/quickstart/)
	1. Including Moonraker configuration
	2. `ls /dev/serial/by-id`
	3. See sample `printer.cfg`
	4. TODO measure Beacon offset direction 
	5. TODO Not doing safe section
	6. Calibrate, via commands in Klipper UI
		1. Home `g28 x y`
		2. Center `G0 X150 Y200`
		3. With paper under nozzle, manually move Z until drags
			1. Beacon RED LED will light
		4. `BEACON_CALIBRATE`
			1. Move up & down -.001
			2. ACCEPT
		5. `BEACON_AUTO_CALIBRATE`
			1. Be sure not to have drag on USB line, will disrupt measure
	7. TODO Finish and do a print
8. Tidy up cabling
	1. Cable can be routed in the cable chain but needs to have distance from the motor wiring due to noise [Source](https://discord.com/channels/641407187004030997/1046570329184669817/1317043210819731487)
9. Reattach bottom right panel

**Config examples**
<a name="how-to-ssh-into-the-printer"></a>
## How to SSH into the printer?
The default username is "pi" and the password is "armbian".

`ssh pi@<your ip address>`

<a name="how-to-install-display-at-top"></a>
## How to install Display at top?

Author(s): @kaihanga

The cables two cables needed for the display don't easily reach the top.

1. Extend cables at bottom
2. Buy [Micro HDMI](https://www.amazon.com/Cablecc-Micro-Female-Extension-Cable/dp/B00S6B8TCQ) and [USB Type-A](https://www.amazon.com/C2G-52119-USB-Extension-Cable/dp/B00CJG2ZYM) Extenders
	1. Yes, it's Mini HDMI and USB Type C at the console but it's micro HDMI and USB Type-A connecting to the Orange PI computer
3. Remove bottom right panel
4. Clip zip ties binding cables
5. Unscrew Z motor; it can be torqued in tough
6. What's first and second here may differ for you
	1. Use needle-nose pliers to remove glue
	2. Pull out cables
	3. Rinse, repeat as necessary
	4. Keep enough cable slack to connect to extenders
7. Carefully pull each cable from top feeding additional cable from the bottom - Don't stress the cables!
8. Check for good slack and the three points: top out for the screen, middle in to take the cables down the rail, and space around the z motor
9. Hook up extensions and mount screen, confirming you have the needed cable length 
10. Reattach Z motor
11. Turn on and test screen works
12. Clean up
	1. Optional - Zip tie cables
	2. Reattach bottom right panel

<a name ="is-there-a-community-to-share-and-learn-about-others-experiences"></a>
## Is there a community to share and learn about other's experience?

There's an "official" discord with an active community. [Click here for an invitation](https://discord.gg/rVUKaBAGKC).

[Information from Peopoly about the community](https://peopoly.net/blogs/news/join-peopoly-discord-community)
