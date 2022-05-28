# WasteHandlerX Robotothon 2022

## Introduction

## Robot platform
- Franka Emika Panda 7-DoF robot
- Ubuntu 18.04 PC
- Intel RealSense2 camera

## Dependencies

- [ROS Melodic](http://wiki.ros.org/melodic/Installation/Ubuntu)
- [MoveIt for melodic](https://moveit.ros.org/install/)
- [intel realsense2_camera & realsense2_description for melodic](https://github.com/IntelRealSense/realsense-ros):
- [libfranka v0.7.0](https://frankaemika.github.io/docs/installation_linux.html)

We also cloned and use our own version of [franka_ros](https://frankaemika.github.io/docs/installation_linux.html) and [panda_moveit_config](https://github.com/ros-planning/panda_moveit_config). 

## Constraints
As the robot is used for other Proof of Concepts, we could not place the robot differently and we had to use the same gripper fingers.

## Improvements to be made

- Add a tip on the side of the gripper to use to lift batteries
- Custom make fingers to make it easier to grasp batteries
- Confirm the task boards position from perception data to increase accuracy.