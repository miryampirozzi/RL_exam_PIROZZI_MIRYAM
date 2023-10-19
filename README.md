# RL_exam_PIROZZI_MIRYAM
RL_exam_PIROZZI_MIRYAM

#Multi-Robot System with Turtlebot3_burger and Kuka_iiwa

This project simulates the navigation of a robot in an industrial environment: it is expected to pick an object, identified by its own marker, and to place it in a target position next to the second robot. This robot must be able to symbolically pick the object and place it on a marker on the floor.

## Features

- Modularity of a multi-robot system
- Server/client service approach

## Getting Started (pre-requirements)

- Ubuntu 20.04
- ROS Noetic
- Gazebo 11

## Packages

This project uses some external packages provided by the course of Robotics Lab at Federico II of Naples and the _aruco-ros_ package. 

## Installation process

In order to run the project, the folder must be cloned inside the _src_folders of the local workspace by opening a terminal in it and running the following commands:

```sh
$ git clone https://github.com/miryampirozzi/RL_exam_PIROZZI_MIRYAM.git
$ cd ..
$ catkin_make -DCATKIN_WHITELIST_PACKAGES="rl_exam"
$ catkin_make -DCATKIN_WHITELIST_PACKAGES=" "
```
## Running the simulation

On five different terminals run the following commands:

- Launch the main node:

```sh
$ roslaunch rl_exam spawn_robots_and_world.launch
```

- Launch aruco node for the detection of the markers:

```sh
$ roslaunch aruco_ros all_aruco.launch
```

- Run the server node:

```sh
$ rosrun rl_exam kuka_invkin_ctrl
```

- Run the client node: 

```sh
$ rosrun rl_exam move_and_search
```

- Open the _rqt_ tool in ROS to visualize the content of some desired topics:

```sh
$ rqt_image_view
```

## Outline

![Client output](/Readme_images/terminal1.png) 
![Server output](/Readme_images/terminal2.png) 
![Simulation results](/Readme_images/final.png) 


## Additional useful information

- In order to properly play the videos included into the pptx presentation, it might be necessary to run the following commands:
  
```sh
$ sudo apt-get update
$ sudo apt-get install ubuntu-restricted-extras
```

- As you have probably noticed, some snapshots of terminals appear to have a different user. That it because it was necessary to run te project on a different hardware by the end of the implementation, since the first one started reporting few issues regarding the kinematic inversion computation.

