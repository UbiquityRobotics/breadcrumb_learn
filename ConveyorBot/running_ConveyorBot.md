---
layout: default
title:  "Running ConveyorBot"
permalink: running_ConveyorBot
---

#### &uarr;[top](https://ubiquityrobotics.github.io/ConveyorBot_learn/)

# Running ConveyorBot

Before the ConveyorBotstarts moving it is necessary to place the markers in the desired location.
[See how to place markers](marker_types_and_placing_them.md).

Initially when robot is boot up, touchscreen display shows an **Loading** screen. After the system is ready you should be able to see a screen with a **START** button.
From initial pose, it will wait for the user to press START and the move to towards the detected marker.
It is important that the robot sees the first marker, otherwise it will not move and pop-up a warning on the screen.

### Basic ConveyorBot Usage

ConveyorBot will smoothly navigate between markers, where each marker arrow should point in the direction of the next marker.
If the robot encounters a STOP marker, it will stop on it and turn in the direction of arrow.
Once robot is on the STOP marker, it will wait until **CONTINUE** is pressed on the touchscreen and then continue driving in the direction of the arrow.
ConveyorBot does not neccesary need to see a next marker from the position on STOP marker.

To make a system work as intended, set of rules should be followed to prevent undesired behaviour.

### Set of Rules

**#1.** Each marker should point in the direction of the next one <br>
**#2.** TURN markers should be used to change driving direction (Crossroads) <br>
**#3.** BIDIRECTIONAL markers should be used for two-way routes, where robot can drive in both directions and not for changing the driving direction. In other words, robot should never come sideways to the BIDIRECTIONAL marker, since it may turn in the wrong direction as intended.<br>
**#4.** GO marker should be used for one-way routes, where robot can drive only in one direction <br>

To run, type:

  `roslaunch ground_fiducials ground_fiducials.launch`

or in Gazebo:

  `roslaunch ground_fiducials sim_ground_fiducials.launch`

ConveyorBot main package are:
- `raspicam_node` that starts onboard Raspberry Pi Camera
- `ConveyorBot_description` that spawns a urdf ConveyorBot model
- `ConveyorBot_detect` for detecting markers and forwarding the pose of the markers
- `ground_fiducials` which handles type of markers
- `ConveyorBot_nav` which handles navigation maneuvers execution

For more advance usage and capabilities refere to [ConveyorBot usage with touchscreen](ConveyorBot_usage_with_touchscreen.md).
