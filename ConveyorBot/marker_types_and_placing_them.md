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

ConveyorBot is enabled to be used either with STag or ArUco markers. The analogy of marker types is the same for both.

Each marker has a unique id, while a number is unique only to the pack denoted in the upper part of the marker as `Pack: X`.
Besides generating packs of fiducial markers, configuration files (.json) named pack-X-info.json are generated inside `ground_fiducials` package, to which the ConveyorBot software will refer to when mapping IDs to NUMBERs.
It is important to have the printed fiducials correspond to the correct .json that was generated at the same time.
This way marker types are correctly distinguished which correspond to the correct ConveyorBot manevers.



## How to place the markers

The most important things to remember before setting up the route of markers are:
- Each marker should point in the direction of the next one
- TURN markers should be used to change driving direction (In the crossroads - multiple markers at one position pointing in different directions)
- BIDIRECTIONAL markers should be used for two-way routes, where robot can drive in both directions and not for changing the driving direction. In other words, robot should never come sideways to the BIDIRECTIONAL marker, since it may turn in the wrong direction as intended.
- GO marker should be used for one-way routes, where robot can drive only in one direction


Markers are sticky stickers that can be peeled off and placed on another floor location. But it is not recommended to peel it off too many times as the glue on the marker can dry out.

An example of a simple marker layout is shown in the figure below.

<img src="ConveyorBot/assets/Map_example1.png" >
