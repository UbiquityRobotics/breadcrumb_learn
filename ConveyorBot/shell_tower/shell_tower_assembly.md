---
layout: default
title:  "Unboxing and Assembling the Tower and the Shell for magni robot"
permalink: shell_tower_assembly
author: Janez Cimerman, Kristjan Povše
---

#### &uarr;[top](https://ubiquityrobotics.github.io/ConveyorBot_learn/)

## Shell and Tower assembly instructions

### Before you begin: 

a) The most important thing to note, is that you always have to have the batteries physically disconnected, while you are doing anything with the cables to prevent any short circuits to the main PCB board – named MCB. To turn off the robot with the provided main switches is not enough.

b) If the Raspberry PI has a micro SD card mounted – avoid powering it on and off too many times, just by cutting off the power. That can lead to microSD card corruption. Always try to either use touchscreen or an SSH connection to shut it down and then cut the power.

c) Screw types used and their names in the instructions:

![Screw Types](bolts.png)

### Assembly process Video

If you prefer to watch a assembly video, follow the links below:
- https://www.youtube.com/watch?v=RDe5XLQTHwM
- https://www.youtube.com/watch?v=O-YKXxbponM

### Assembly process

<!-- The original plan for ConveyorBot is that is works only with sonars (for safety stopping) but they really are not reliable so we are also including the LIDAR into the design for now so we have a safe alternative at least for the first couple of customers -->

1. Remove the top plate and the Sonar board from the robot by unscrewing it and disconnecting the flat cable. Also unscrew the camera from its holder (4xM2 screws) – the camera is going to be remounted onto the Tower later. Here if the picture of how the robot looks without the sonars and camera. 
Note the batteries orientation - they need to have terminals at the back of the robot as shown (This is to ensure easy of reconnecting main power cable when shell in mounted).

    ![Base Robot Without The Camera](https://user-images.githubusercontent.com/53408077/127979241-25dc71c2-dab8-4a5d-acd6-eb58c3729061.jpg)

2. Connect the LIDAR molex power connector like shown - INTO THE LEFT MOLEX CONNECTOR and the LAN cable into the RPI LAN port.

    ![Molex Connector](molex_lidar_conn.jpg)

    In this tutorial we are going to mount it on the left side of the shell (there are more positions available - [see picture](lidar_mounts2.png)). Guide the lidar cable through the sheet metal holder hole, like shown in the picture. 

    ![Lidar Cable Guide](https://user-images.githubusercontent.com/53408077/127979821-400f1209-d761-4cf3-9155-169bef946041.jpg)


3. Mount the two shell switches and connect the cables. Red ESTOP button is assembled from two separate pieces. To install, first disassemble it by turning red and black "mushroom" part counter-clockwise and pulling it upwards. Put the "mushroom" part thro the hole in the shell like shown.

    ![Disassembled ESTOP](https://user-images.githubusercontent.com/53408077/127981007-8b6c83c5-acd2-4087-aebe-32a92b743f72.jpg)


    Assemble the estop button by pushing it lightly inwards and turn it clockwise (This part should go together easily without unnecessary force) . Note that the shell does not have screw holes for mounting the ESTOP button, the screws just push on the shell to keep the button in place.

    ![Emg Assemble](emg_assemble.jpg)
        
    Make sure to take note where which cable is going to the emergency and which into the power switch (CABLE COLORS MAY WARY).

    ![Switches Shell Cables](switches_shell_cables.jpg)

4. Mount the LIDAR holder using 2xM5 socket screws.

    ![Lidar Holder](lidar_holder.jpg)

5. Put the shell on the robot.

    ![Shell On Robot](shell_on_robot.png)

6. Connect the shell switches into the switch board – emergency button behind the red switch and square shell switch behind the black one (CABLE COLORS MAY VARY).

    ![Switch Connection](switch_connection.jpg)

7. Connect the LIDAR

    ![Lidar Connection](lidar_connection.png)

8.  Screw the LIDAR with 4xM3 socket screws

    ![Lidar Screw](lidar_screw.png)

***

### Tower assembly

In this section it is shown how to assemble the Tower 

1. Take the shown sheet metal parts and use 4xM2 phillips screws to mount the camera and 4xM3 short socket screws to mount the touchscreen holders.

    ![Touchscreen Holders](touchscreen_holders.png)

1. Connect the two flat cables and one USB cable as shown. Notice how the blue sides of the flat cable connectors are turned – camera outward and screen inward. Please also make extra sure, that the flat cable connectors are well connected and as fully pressed into the connectors as possible. A lot of times, this connection being not adequate or faulty is the reason screen or camera don't work. You can test this connections (by following steps in the [Connecting The Tower To Shell](#connecting-the-tower-to-shell) Section below) by connecting to RPi and powering it up to see if the screen and camera are working - to avoid having to reassemble everything up again later. Here it is useful to use a sharpie to indicate which flat cable is connected to camera and which to the screen.

    ![Flat Cables](flat_cables.png)

2. Now use the 4xM3 socket screws to mount the screen into the back plate. You can use a zip tie to mount the USB cable into the housing using the square holes.

    ![Screen Back Screw](screen_back.png)


3. Use 6xM5 socket screws to put the two angle parts of the tower together

    ![Angle Parts](angle_parts.jpg)

4. Use 4xM3 socket screws to mount the screen assembly onto the angle assembly. Place the USB cable and screen flat cable into one cable duct (TODO CABLE DUCT ON THE PICS) and the camera flat cable into the other.

    ![Screen To Angle](screen_to_angle.jpg)

5. As the last part of the tower assembly, mount the front panel using 4xM3 socket screws.

    ![Screen Front Screw](screen_front.jpg)
    
1. The cables can also be inserted into cable guides

    ![Cable Guides](cable_guides.png)

***

### Connecting The Tower To Shell

1. Put the assembled tower onto the robot. Be careful with the fragile flat cables.

    ![Tower On Shell](tower_on_shell.png)

2. If you haven't already, please MAKE SURE THE BATTERIES ARE DISCONNECTED FROM THE ROBOT before continuing. Connect the two flat cables to Raspberry Pi (RPi). The screen flat cable connector is at the back and for camera in the middle of RPi. Notice that the blue part of the flat cable connector is pointed backward (touching black latch) for the screen cable and to the front for the camera cable. Make sure that these cables are pushed into the RPI as far as possible – a lot of people have problems when these connectors are not properly connected.

    ![RPI Connect 1](rpi_connect1.png)

    ![RPI Connect 2](rpi_connect2.png)

3. Connect the RPI back into the MCB board

    ![RPI to MCB](rpi_to_mcb.png)

4. Connect and fold the USB cable

    ![USB cable](usb_cable.jpg)

5. Before screwing the rest of the robot, try powering it up, to see if the screen and the camera work. You can do that by 1.) first make sure emergency switch is pressed inside and square switch is switched off, 2.)connecting the RED battery cable connector, 3.) switching on the square switch on the shell. The screen should be lighting up and after the robot boots, you should see camera stream on the WebApp. If anything does not work, the fault, most probably is the bad connections of the flat cables – recheck those. Turn off the robot and disconnect the RED battery connector before continuing.
 
    The screen should be lighting up and after the robot boots you should see camera stream by clicking the Screen icon on the Conveyorbot app. The camera stream might not show up immediately - please wait at least until the battery icon shows some battery charge. If anything does not work, the fault, most probably is the bad connections of the flat cables – recheck those. Turn off the robot and disconnect the RED battery connector before continuing.

    ![Connection Test](connection_test.png)

    ![Camera Stream](camstream.jpg)

    If everything went well touch the camera stream to exit and shutdown the RPI, wait 20 seconds for RPI to properly shutdown and then again disconnect the red battery cable before proceeding.

6. Use 4xM4 socket screws to mount the front plate

    ![Front Plate](front_plate.png)

7. Mount the charging port cover

    ![Charging Cover](charging_cover.png)


8.  Use 6xM6 socket screws to mount the tower and the shell to the robot. 

    ![Tower to Shell Mount](mount_tower_to_shell.png)

    You can use 10xM5 button socket screws and 4xM5 socket screws to mount the shelves.

    ![Shelves Mount](shelves_mount.png)


9.  Mount black grommets into the empty LIDAR connector holes. Side point: more LIDAR positions are available. All those can be used, but then an easy parameter change needs to be done in the system of the robot.

    ![Lidar Mounts](lidar_mounts.png)

    ![Lidar Mounts 2](lidar_mounts2.png)


10. Wherever you mounted your lidar, make sure the system knows about its location on the robot by SSH-ing into the robot and then editing the following folder
 
        sudo nano /etc/ubiquity/robot.yaml
    
    And the lidar position should be changed to the proper one. In this tutorial the lidar was mounted on the left side of the shell. Position of the camera should be downward

        lidar: {'position' : 'shell_left'} # possible: none, top_plate, shell_left, shell_right, shell_center, tower_center


11. You can now reconnect the battery with the red connector, power up the robot and begin using it. Remember to every time in the future you need to reconnect something first disconnect the red battery connector.



## Bolt BOM
### Screen
- 4xM3x10mm Cap socket - Screen Top
- 4xM3x10mm Cap socket - Screen Base
- 4xM3x10mm Cap socket - Screen to base
- 4xM3x4mm Cap socket - Screen to holders
- 4xM2 Philips round - Camera

### Tower
- 5xM5x10mm Button socket - Bottom shelf
- 5xM5x10mm Button socket - Top shelf
- 4xM5x14mm Cap Socket - Angle shelf holder
- 6xM6x15mm Cap Socket - Mounting tower onto the shell

### Shell
- 4xM4x10mm Cap socket - shell side cover
- 4xM4x12mm Cap Socket - Front cover
- 2xM4x13mm Thumb screw - front charging cover (with black plastic for easy twisting)
- 2xM5x14mm Cap Socket - Lidar holder to shell
- 4xM3x8mm Cap Socket - Lidar screws
- 3x Grommet (black rubber to cover lidar holes with)

## Electrical BOM
- 1x Emergency switch
- 1x Emergency switch cable
- 1x Shell Power switch
- 1x Shell Power switch cable
- 1x USB mcro cable
- 2x Flat cable 1m
## Mechanical Parts BOM

![Mechanical Parts](mechanical_parts.jpg)

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