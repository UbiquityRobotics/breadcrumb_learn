---
layout: default
title:  "Running in Gazebo"
permalink: gazebo
---

#### &uarr;[top](https://ubiquityrobotics.github.io/ConveyorBot_learn/)

# Running in Gazebo

Before launching in Gazebo, you need to generate the markers that you will place in the simulation world.
Our fiducials generators provide you a simple UI to do this.

## Fiducials Model Generator
Arbitrary ranges of Fiducial marker Gazebo models can be generated with /scripts/fiducial_generator/fiducial_gen.py

This script populates /models directory.
Before launching the Gazebo simulation, add to ~/.bashrc or enter to terminal:

    export GAZEBO_MODEL_PATH=${GAZEBO_MODEL_PATH}:~/catkin_ws/src/ConveyorBot/ConveyorBot_gazebo/models

Launch files enable you to run the Gazebo, RViz and add our ConveyorBot robot in it. Additionally a simple controller opens up with which you can drive the ConveyorBot around.

## Launch files

There are several demo worlds you can use to get familiar with the ConveyorBot functionality. They can be found in `worlds` directory.
To run them use:

    roslaunch ConveyorBot_gazebo fiducial_world.launch world_name:=<WORLD-NAME>.world

If `world_name` is left empty launch files runs by default a world with robot and a markers route.

add to ~/.bashrc or enter to terminal before launching (modify the path so it will point to /models directory in ConveyorBot_gazebo):

    export GAZEBO_MODEL_PATH=/catkin_ws/src/ConveyorBot/ConveyorBot_gazebo/models

Make sure the directory is populated with fiducial models before hand. If not, go to `scripts/fiducial_generator` directory and run:

    python fiducial_gen.py

This scripts will generate everything necessary to spawn a fiducial into Gazebo simulation.


## Fiducial follow

In order for the robot to start moving according to the markers, run:

    roslaunch ground_fiducials sim_ground_fiducials.launch touchscreen:=false mode:=general_mode

Where you can determine mode and whether you want to use touchscreen.

If touchscreen is used, consider reading the section below.

### Touchscreen UI

Run [`ConveyorBot_touchscreen`](https://github.com/UbiquityRobotics/ConveyorBot/tree/indigo-devel/ConveyorBot_touchscreen)
on your local workstation. If you want to make sure it will not launch Chromium in kiosk mode then open Chromium before running `ConveyorBot_touchscreen`.

```
roslaunch ConveyorBot_touchscreen touchscreen_rosbridge.launch
```
