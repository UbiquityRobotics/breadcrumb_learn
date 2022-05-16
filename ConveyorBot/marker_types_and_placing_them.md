---
layout: default
title:  "Marker types and placing markers in the desired location"
permalink: marker_types_and_placing_them
---

# Marker types and placing markers in the desired location


The ConveyorBot is navigating itself using our floor stickers called Fiducials. There are several types of Fiducials:

| Marker type        | Image           |
| ------------- |:-------------:|
|  **Go marker**  has a single arrow which point to the direction where the ConveyorBot will drive. | <img src="ConveyorBot/assets/go_marker.jpg" >  |
|  **Stop marker** is made to halt the ConveyorBot in that spot. After the ConveyorBot moves on top of the Stop marker it rotates in a direction of a marker arrow. While ConveyorBot waits on a Stop marker the user can load or unload the packages. The robot will resume following markers when user presses the CONTINUE button on the touchscreen of the ConveyorBot. | <img src="ConveyorBot/assets/stop_marker.jpg" >  |
|  **Turn marker** is made for creating crossroads. Crossroad is a couple of markers in the same location (they must not overlap!), where each is pointing in an arbitrary/different direction. Purpose of Turn markers and crossroads is to change the driving direction of the ConveyorBot. | <img src="ConveyorBot/assets/turn_marker.jpg" >  |
|  **Bidirectional marker** is the only marker with 2 arrows in it. ConveyorBot drives allong the arrow that requires less robot rotation. Bidirectional marker is good for two-way routes where ConveyorBot requires to move in both directions for example narrow aisles where there is not enough space for both a forward and return path. | <img src="ConveyorBot/assets/bidirectional_marker.jpg" >  |

ConveyorBot is enabled to be used either with STag or ArUco markers. The analogy of marker types is the same for both. The recommended and default type of markers is STag.

Each marker has a unique id, which is written on it. This way marker types are correctly distinguished which correspond to the correct ConveyorBot manevers.

## How to place the markers

The most important things to remember before setting up the route of markers are:
- Each marker should point in the direction of the next one
- TURN markers should be used to change driving direction (In the crossroads - multiple markers at one position pointing in different directions)
- BIDIRECTIONAL markers should be used for two-way routes, where robot can drive in both directions and not for changing the driving direction. In other words, robot should never come sideways to the BIDIRECTIONAL marker, since it may turn in the wrong direction as intended.
- GO marker should be used for one-way routes, where robot can drive only in one direction
- Before sticking markers to the ground with their glue, it is recommended to paste them to the ground with a tape, so that you can test if your route setup is correct. After testing the route, stick them onto the ground normally.


Markers are sticky stickers that can be peeled off and placed on another floor location. But it is not recommended to peel it off too many times as the glue on the marker can dry out.

An example of a simple marker layout is shown in the figure below.

<img src="ConveyorBot/assets/Map_example1.png" >

## Circuit route

If you want multiple robots to drive on the same marker setup, you should arrange the markers in a so called "Circuit route", so that the robots won't collide into each other. This type of marker setup is recommended also if you have only one robot, because you never know when you will add another robot to your fleet. The Circuit route has an inbound and an outbound path. Inbound serves as the path for robots to drive to the goal and the outbound is the path which is used for the robots to return back to the starting point. The inbound and outbound paths should be at least 1 meter apart (TODO: determine the exact minimum distance), so that the robots won't obstruct each other. On both ends of the path, markers should be arranged in a specific way, shown in the bellow image.
When setting up a route, the measurements from the bellow image need to be considered (TODO: test extensively if the measurements in the image are actually correct and update the values if necessary).
If you want to include a STOP marker into the Circuit route, the best way of placing it is one meter behind the GO marker. You don't place the STOP marker 4 meters away from GO marker, because you might want to ignore the STOP marker in the case if you don't want the robot to stop on it. This would lead to 8 meters distance between GO markers, which is too far apart, if the STOP marker would be 4 meters away from previous and following GO marker.
As seen from the image, on each end of the Circuit route, there is a TURN marker, which you need to include into the route on the touchscreen. This can't be a GO marker, because it would be ignored as it is turned in opposite direction as the robot's driving direction.

<img src="ConveyorBot/assets/Map_example_circuit.png" >

### Branches from main circuit route

TODO: Desribe this after collision avoidance when returning on the main route from a branch is done.

## Ignored opposite markers

By default, the GO and STOP markers which are rotated in the opposite direction as the robot is driving are ignored. This is required for the Circuit route to work correctly when inbound and outbound paths are close together, becasue otherwise, if the robot is driving on the inbound path, it might detect and follow the opposing markers from the outbound path.

