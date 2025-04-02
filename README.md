![image](https://github.com/user-attachments/assets/b82db5cf-3603-45b4-8d65-524a943a879d)


![image](https://github.com/user-attachments/assets/cab7eb79-8321-4487-9588-2db5ac1d2235)

Materials required:
9 x 4mm ID 20mm OD washers 
9 x 20mm M4 Countersunk screws (18mm length also fine)
9 x 4mm ID 16mm OD 12mm height silicone spacers (Typically sold for i3 3d printer beds to replace springs)
https://www.aliexpress.com/item/1005007045883147.html
 ![image](https://github.com/user-attachments/assets/c2a88624-3c5f-48f4-8351-21e68db8acea)

Tools of benefit:
Calipers
9mm or 10mm hole punch
Bolt hole finder https://www.printables.com/model/950417-sovol-sv08-bed-bolts-finder 

1.	Disconnect your printer from mains power.

2.	Open the bottom of your printer, disconnect the bed heating cables from the power board. *Exercise caution when working with the printer’s power supply circuits, do not touch capacitors*

 ![image](https://github.com/user-attachments/assets/038436db-549b-4eb2-8fb2-5c2820ccce38)

There is an additional ground cable spliced in that runs to the 2020 extruded frame that must also be removed.

3.	Disconnect the bed thermistor from the motherboard.

4.	Return the printer upright.

5.	Use the printers bolt hole finder tool, or use the below file to create a paper template to find all 9 bolt holes and mark them on your magnetic sheet.
https://www.printables.com/model/1148161-sovol-sv08-aluminium-bed-magnetic-bed-surface

6.	Remove holes in the magnetic sheet by cutting them to get to the aluminium bed bolts.
Either use hole punches of appropriate size, by pressing them into the magnetic sheet and twisting. *Do not punch the holes by hammering them* this will damage the aluminium bed and potentially the rest of your printer. The magnetic sheet is soft enough that you can cut the holes by pressing down by hand and rotating. Alternatively, use a sharp craft knife to cut the holes.
(There’s a 10th screw in the bottom left, but this if for the ground wire on the bottom and does not need removing)

 ![image](https://github.com/user-attachments/assets/b5868ac2-a7cd-4b43-89e4-5e9e45885a31)


7.	Undo all 8 screws that you have just uncovered. Yes, 8. Sovol did not include the center stock screw.

8.	Separate the aluminium bed from the plastic mount. This will take some force to pry off as the excess edges of the magnetic sheet are held down onto the edge of the plastic mount by double sided adhesive tape.

9.	Trim the edges of the magnet sheet that overhang the aluminium sheet.

10.	On the plastic bed mount, place 1 washer on each plastic standoff peg.
These may easily get knocked off during installation so I prefer to glue these down. Place a small ring of superglue round the edge of each standoff, carefully avoiding getting any superglue in the threads. Place a washer on top and then temporarily secure the washer in place by tightening down the short stock M4 screw that we just removed until the glue dries. Then remove the screws once more. 
 

 ![image](https://github.com/user-attachments/assets/11f8590b-5c05-4645-9057-46eeb5c38dad)


![image](https://github.com/user-attachments/assets/d8ddafef-3c05-4ca7-a50d-84f215edf08b)



11.	Place the M4x20mm countersunk screws through all 9 mount points in the aluminium bed.

12.	Put a single silicone spacer on the bottom side of the aluminium bed screw.
Alternatively, balance them on top of each washer, these may be glued, whichever you find easiest for the next step.
 
![image](https://github.com/user-attachments/assets/c5b17b7f-4724-453d-aed2-81f4222dd749)

13.	Lower the aluminium bed onto the plastic bed mount, ensuring the silicone spacers stay in place and the screws locate their way into the washers.
The components should be sandwiched as follows.

 ![image](https://github.com/user-attachments/assets/11ed59f5-0702-4f25-b9c9-d319837fadc0)


14.	Tighten all 9 screws down, until you meet some resistance. Then give them all a few extra turns until you can see them bulge slightly. This tension and resistance is what we rely on to push back against the bed to dewarp it and fix the infamous taco shape. You want the resistance on the screws to all feel roughly the same to start out with. 

![image](https://github.com/user-attachments/assets/6c9e9e10-d5e6-4ebd-b0d9-e2de0d68784c)
![image](https://github.com/user-attachments/assets/ae15eb95-220b-4dd3-8394-4fa604772c53)

15.	Flip the printer to get to the base to reassemble the bed’s power cables. Use the reference image from step 2.

16.	Return the printer upright.

17.	Ensure that the build plate is reinstalled to protect the magnetic sheet.

18.	Connect the printer to mains and power it on.

19.	Add the following to your printer.cfg to add assisted bed tramming.
[bed_screws]
screw1: 175,175
screw1_name: Centre
screw2: 13,13
screw2_name: FrontLeft
screw3: 176,13
screw3_name: FrontMid
screw4: 338,13
screw4_name: FrontRight
screw5: 13,176
screw5_name: MidLeft
screw6: 338,176
screw6_name: Mid Right
screw7: 13,338
screw7_name: BackLeft
screw8: 176,338
screw8_name: BackMid
screw9: 338,338
screw9_name: BackRight
horizontal_move_z: 2
speed: 400
probe_speed: 3

[screws_tilt_adjust]
screw1: 191,166
screw1_name: Centre
screw2: 28,3
screw2_name: FrontLeft
screw3: 191,3
screw3_name: FrontMid
screw4: 353,3
screw4_name: FrontRight
screw5: 28,166
screw5_name: MidLeft
screw6: 353,166
screw6_name: Mid Right
screw7: 28,328
screw7_name: BackLeft
screw8: 191,328
screw8_name: BackMid
screw9: 353,328
screw9_name: BackRight
horizontal_move_z: 2
speed: 400
screw_thread: CCW-M4

The [bed_screws] section tells Klipper the location of the actual screws and the [screws_tilt_adjust] tells Klipper where to locate the nozzle so that the probe is as close above the screws as possible. 
You can work this out by taking the screw location and adjusting it by the probe x and y offset

20.	Save the printer.cfg and then either save and restart or send save_config in the console.

DO NOT PERFORM QUAD GANTRY LEVEL until we reach a stage later on when this is instructed.

21.	Manually tram your gantry. 
Either with the plastic chassis at the bottom or with the frame at the top. You need to tram the gantry square by lowering and raising each corner by hand until they are all the same height distance to a static part of the printer that is not the bed. Spend a lot of time on this until you are very satisfied that it is all square. We do this because we are going to then tram the bed to the gantry in the next step.


22.	Send the command ‘SET_KINEMATIC_POSITION Z=0’
This lets us move the z steppers without homing.

23.	Move the gantry up a small amount to engage the steppers and lock your tram in place. 
Either through web/screen interface or the command ‘_CLIENT_LINEAR_MOVE Z=10 F=1500’

24.	Measure your tram again, ensure you’re still happy with it.
Adjust as follows to make any small corrections using these console commands

Move Z3, the front left stepper:
FORCE_MOVE STEPPER=stepper_z DISTANCE=<value> VELOCITY=1

Move Z4, the front right stepper:
FORCE_MOVE STEPPER=stepper_z3 DISTANCE=<value> VELOCITY=1

Move Z1, the back right stepper:
FORCE_MOVE STEPPER=stepper_z1 DISTANCE=<value> VELOCITY=1

Move Z2, the back left stepper:
FORCE_MOVE STEPPER=stepper_z2 DISTANCE=<value> VELOCITY=1

Note that the labels on the printer do not match the stepper name number as defined in Klipper’s config.

25.	Heat the bed to your typical print temperature and wait for 15-20 minutes to heatsoak.
60c for PLA, 100c for ABS etc.

26.	Home the printer.
AGAIN, DO NOT PERFORM A QGL OR THIS WILL UNDO YOUR MANUAL TRAM!

27.	Send the command ‘screws_tilt_calculate’
The printer will now go and probe the build plate above each screw location.

28.	Klipper will return the adjustments values. These work like a clock. Giving you a rotation distance to turn each screw with your hex key. For example 00:30 is 180 degrees, 00:15 is 90 degrees, 1 is a full rotation of 360 degrees. 00:40 is 225 degrees. CW and CCW denote clockwise and counter-clockwise. 
_It's goig to read the height of the centre screw as the value it compares all outer screws too, so if you want to squish the bed down further, giving the spacers more compression, start with making the centre screw as tight as you are happy with. This process will then bring the rest in line with that._

29.	Remove the build place and make adjustments as guided. If you need to access the last screw which is covered by the toolhead, do not disable the steppers or you may lose your tram. Send commands to move the toolhead up and then across x to reveal the final screw.

30.	Ensure that the build plate is reinstalled to protect the magnetic sheet.

31.	Repeat steps 26-30 until you reach a satisfactory level. It is reasonable to reach the printer reporting values 00:00 – 00:05 by hand adjustments, depending on how patient and granular you are. The closer these values are all to 0, the flatter your bed will be.

32.	Home the printer.
Since the corners of the gantry and the corners of the bed are now nicely trammed and everything should be relatively square to the frame and chassis, it’s now safe to allow quad_gantry_level commands.

33.	Run a bed mesh scan.

34.	 Read your height map, specifically look at the values for each corner screw and compare it to the centre. Each corner should match roughly. Hopefully the centre does too. If so, great, if your range is under 0.2mm this is acceptable. Anything closer to 0.1mm is a huge bonus. You can stop here.































