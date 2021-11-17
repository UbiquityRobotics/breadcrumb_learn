---
layout: default
title:  "Unboxing and Assembling the Tower and the Shell for magni robot"
permalink: shell_tower_assembly
author: Janez Cimerman, Kristjan Povše
---

#### &uarr;[top](https://ubiquityrobotics.github.io/ConveyorBot_learn/)

## Shell and Tower assembly instructions - WITHOUT SONARS

Shell and Tower assebly with sonars - TBA

### Before you begin: 

a) **!!! ALWAYS DISCONNECT THE CABLE FROM THE BATTERIES BEFORE DOING ANYTHING WITH ELECTRONICS !!!** The most important thing to note, is that you always have to have the batteries physically disconnected, while you are doing anything with the cables or electronics to prevent any short circuits to the main PCB board. Turning off the robot with the provided main switches is not enough. **Failing to do this can result in injuries and/or fried electronics!**

b) If the Raspberry PI has a micro SD card mounted – avoid powering it on and off too many times just by cutting off the power. That can lead to microSD card corruption. Always try to either use touchscreen or an SSH connection to shut it down and then cut the power.

c) Screw types used and their names in the instructions:

![Screw Types](bolts.png)

### Assembly process Video

Here are two videos of how assembly looks like, all detailes can be found further in the instructions.
- https://www.youtube.com/watch?v=RDe5XLQTHwM
- https://www.youtube.com/watch?v=O-YKXxbponM

### Assembly process

<!-- The original plan for ConveyorBot is that is works only with sonars (for safety stopping) but they really are not reliable so we are also including the LIDAR into the design for now so we have a safe alternative at least for the first couple of customers -->

1. Remove the top plate and the Sonar board from the robot by unscrewing it and disconnecting the flat cable. Also unscrew the camera from its holder (**4xM2 screws**) – **the camera is going to be remounted onto the Tower later**. Here if the picture of how the robot looks without the sonars and camera. 
Note the batteries orientation - they need to have terminals at the back of the robot as shown (This is to ensure easy of reconnecting main power cable when shell in mounted).

    ![Base Robot Without The Camera](https://user-images.githubusercontent.com/53408077/127979241-25dc71c2-dab8-4a5d-acd6-eb58c3729061.jpg)

2. Connect the LIDAR molex power connector like shown - INTO THE LEFT MOLEX CONNECTOR and the LAN cable into the RPI LAN port.

    ![Molex Connector](molex_lidar_conn.jpg)

    In this tutorial we are going to mount it on the left side of the shell (but there are other lidar positions available - [see picture](lidar_mounts2.png)). Guide the lidar cable through the sheet metal holder hole, like shown in the picture. 

    ![Lidar Cable Guide](https://user-images.githubusercontent.com/53408077/127979821-400f1209-d761-4cf3-9155-169bef946041.jpg)


3. Mount the two shell switches and connect the cables. Red ESTOP button is assembled from two separate pieces. To install, first disassemble it by turning red and black "mushroom" part counter-clockwise and pulling it upwards. Put the "mushroom" part thro the hole in the shell like shown.

    ![Disassembled ESTOP](https://user-images.githubusercontent.com/53408077/127981007-8b6c83c5-acd2-4087-aebe-32a92b743f72.jpg)


    Assemble the estop button by pushing it lightly inwards and turn it clockwise (This part should go together easily without unnecessary force). Note that the shell does not have screw holes for mounting the ESTOP button, the screws just push on the shell to keep the button in place.

    ![Emg Assemble](emg_assemble.jpg)
        
    Plug the black cables into the power switch and red ones into the EMG switch. Use the self-adhesive cable clip to fix the cables in place (red arrow). If the cable clip is not already attached it should be found in one of the zip bags.

    ![Shell Buttons Clip](shell_buttons_clip.jpg)

4. Mount the LIDAR holder using **2xM5x15mm Cap Socket** screws from SHELL zip bag (red arrows). Also unscrew the front plate and save the 4 screws that hold it in place (green arrow).

    ![Lidar and Front plate](lidar_front_plate.jpg)

5. Put the shell on the robot.

    ![Shell On Robot](shell_on_robot.png)

6. Connect the shell switches into the switch board – emergency button behind the red switch and square power shell switch behind the black one.

    ![Switch Cables](switch_cables.jpg)

    Make sure that the black button here is pressed in while the red one is released.

    ![Switchboard](switchboard.jpg)

7. Connect the LIDAR

    ![Lidar Connection](lidar_connection.png)

8.  Screw the LIDAR with **4xM3x8mm Cap Socket** screws from the SHELL zip bag.

    ![Lidar Screw](lidar_screw.png)

***

### Tower assembly

1. Some touchscreen parts come pre assembled witch some cables already attached and tucked inside (purple arrow). First unscrew and save 4xM3x15mm screws (red arrows)

    ![Touchscren pre assebled](touchscreen.jpg)

2. Attach the camera with 4xM2 screws that it came attached to the robot with. If the bolt is hard to screw, simply tighten and untighten it a couple of times until it gets easier. After that attach the flat cable to the camera.

    ![Flat Cables](flat_cables.png)

    Notice how the blue sides of the flat cable connectors are turned. Please also make extra sure, that the flat cable connectors are well connected and as fully pressed into the connectors as possible (red arrow) with the connector lock pressed in (purple arrows).

    ![Camera](cam_attach.jpg)

    Also use a sharpie or some other tool to indicate the camera flat cable to be able to distinguish the cables later.
 

3. A lot of times the flat cable connections being not adequate or faulty is the reason screen or camera don't work. You can test this connections (by following steps in the [Connecting The Tower To Shell](#connecting-the-tower-to-shell) Section below) by connecting to RPi and powering it up to see if the screen and camera are working - to avoid having to reassemble everything up again later.

4. Now use the **4xM3x15mm Cap Socket screws** from step 1. to mount the screen into the back plate. You can use a zip tie to mount the USB cable into the housing using the square holes.

    ![Screen Back Screw](screen_back.png)


5. Use **6xM5x15mm Cap Socket screws** from TOWER zip bag to put the two angle parts of the tower together. 

    The holes in two parts might not always fully allign if the parts are just out of the box. If that is the case first screw the front two screws tightly and then use a bit of force to also screw the others. The parts should fit together with a bit of effort. 

    ![Angle Parts](angle_parts.jpg)


6. Use **4xM3x15mm Cap Socket screws** from SCREEN zip bag to mount the screen assembly onto the angle assembly. At this point you can also unglue the protective sticker from the touchscreen if you wish.

    ![Screen To Angle](screen_to_angle.jpg)

7.  As the last part of the tower assembly, mount the front panel using **4xM3x15mm Cap Socket screws** from SCREEN zip bag.

    ![Screen Front Screw](screen_front.jpg)
    
8.  The cables can also be inserted into cable guides. 

    ![Cable Guides](cable_guides.png)

***

### Connecting The Tower To Shell

1. Put the assembled tower onto the robot. Be careful with the fragile flat cables.

    ![Tower On Shell](tower_on_shell.png)

2. If you haven't already, please **MAKE SURE THE BATTERIES ARE DISCONNECTED FROM THE ROBOT** before continuing. Connect the two flat cables to Raspberry Pi (RPi). The screen flat cable connector is at the back and for camera in the middle of RPi. Notice that the blue part of the flat cable connector is pointed backward (touching black latch) for the screen cable and to the front for the camera cable. Make sure that these cables are pushed into the RPI as far as possible – a lot of people have problems when these connectors are not properly connected.

    ![RPI Connect 1](rpi_connect1.png)

    ![RPI Connect 2](rpi_connect2.png)

3. Connect the RPI back into the MCB board. Make very sure that the RPI pins are not off by 1 pin in any direction with respect to the MCB connector! 

    ![RPI to MCB](rpi_to_mcb.png)

4. Connect and fold the USB cable

    ![USB cable](usb_cable.jpg)

5. Before screwing the rest of the robot, try powering it up, to see if the screen and the camera work. You can do that by 
    
    1.) first make sure emergency switch is pressed inside and square switch is switched off, 
    
    2.)connecting the RED battery cable connector, 
    
    3.) switching on the square switch on the shell. The screen should be lighting up and after the robot boots, you should see camera stream on the WebApp. If anything does not work, the fault, most probably is the bad connections of the flat cables – recheck those. Turn off the robot and disconnect the RED battery connector before continuing.
 
    The screen should be lighting up and after the robot boots you should see camera stream by clicking the Screen icon on the Conveyorbot app. The camera stream might not show up immediately - please wait at least until the battery icon shows some battery charge. If anything does not work, the fault, most probably is the bad connections of the flat cables – recheck those. Turn off the robot and disconnect the RED battery connector before continuing.

    ![Connection Test](connection_test.png)

    ![Camera Stream](camstream.jpg)

    If everything went well touch the camera stream to exit and shutdown the RPI, wait 20 seconds for RPI to properly shutdown and then again disconnect the red battery cable before proceeding.

6. Use **4xM4x8mm Cap Socket screws** which you unscrewed before to mount the front plate back.

    ![Front Plate](front_plate.png)

7.  Mount the charging port cover if its not mounted already.

    ![Charging Cover](charging_cover.png)


8.  Use **6xM6x15mm Cap Socket screws** from TOWER zip bag to mount the tower and the shell to the robot. 

    ![Tower to Shell Mount](mount_tower_to_shell.png)

    You can use **4xM5x15mm Cap Socket screws** to mount the angle shelf holder and **10xM5x15mm button socket screws** to mount the two shelves.

    ![Shelves Mount](shelves_mount.png)


9.  Mount black grommets into the empty LIDAR connector holes. Side point: more LIDAR positions are available. All those can be used, but then an easy parameter change needs to be done in the system of the robot.

    ![Lidar Mounts](lidar_mounts.png)

    ![Lidar Mounts 2](lidar_mounts2.png)


10. Wherever you mounted your lidar, make sure the system knows about its location on the robot by SSH-ing into the robot and then editing the following folder
 
        sudo nano /etc/ubiquity/robot.yaml
    
    And the lidar position should be changed to the proper one. In this tutorial the lidar was mounted on the left side of the shell. Position of the camera should be downward

        lidar: {'position' : 'shell_left'} # possible: none, top_plate, shell_left, shell_right, shell_center, tower_center


11. You can now reconnect the battery, power up the robot and begin using it. Remember to every time in the future you need to reconnect something first disconnect the red battery connector.

## Bolt BOM
  - 3x Grommet 20mm (black rubber to cover lidar holes with) LINK
  - 4x 	M6 x 2-2.5mm thick washers -  temporary replacement for Shell Distancers (2-2.5mm thickness whichever is available) LINK
  - 4x	M3x5mm Cap Socket
  - 12x	M3x15mm Cap Socket
  - 4x	M3x8mm Cap Socket
  - 8x	M4x8mm Cap Socket
  - 2x	M4x8-10mm Thumb Screw (8 or 10 mm whichever is available)
  - 12x	M5x15mm Cap Socket
  - 10x	M5x15mm Button Socket
  - 6x	M6x15mm Cap Socket
## Electrical BOM
  - 1x Touchscreen
  - 1x Emergency switch custom cable (red wires)
  - 1x Power switch custom cable (black wires)
  - 1x Black Shell Power switch
  - 1x USB mcro cable 1m
  - 2x Flat cable 1m
  - 1x Adhesive Cable clip
## Mechanical Parts BOM
  1. 1x Shell
  2. 1x Lidar Mount
  3. 1x Touchscreen Back Cover
  4. 1x Tower Angle Front
  5. 1x Touchscreen Front Cover
  6. 1x Top Shelf Holder
  7. 1x Tower Angle Bottom
  8. 2x Shelves
  9. 1x Front Shell Cover
  10. 1x Front Charger Cover
  11. 1x Battery Shell Cover
  12. 2x Touchscreen Holders
  13. 2x Shell Distancers

![Mechanical Parts](mechanical_parts.jpg)