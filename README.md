# WasteHandlerX Robotothon 2022

## Robot platform
- Franka Emika Panda 7-DoF robot
- Ubuntu 18.04 PC
- Intel RealSense D435 camera

## Dependencies

- [ROS Melodic](http://wiki.ros.org/melodic/Installation/Ubuntu)
- [MoveIt for Melodic](https://moveit.ros.org/install/)
- [Intel RealSense2 camera & description for Melodic](https://github.com/IntelRealSense/realsense-ros)
- [libfranka v0.8.0](https://frankaemika.github.io/docs/installation_linux.html)
- [OpenCV](https://opencv.org/)
- [librealsense](https://github.com/IntelRealSense/librealsense)

We also cloned and use our own version of [franka_ros v0.8.0](https://frankaemika.github.io/docs/installation_linux.html) and [panda_moveit_config](https://github.com/ros-planning/panda_moveit_config). 

## Constraints
As the robot is used for other Proof of Concepts, we could not place the robot differently and we had to use the same gripper fingers.

## Improvements to be made

- Add a tip on the side of the gripper to use to lift batteries
- Custom make fingers to make it easier to grasp batteries
- Confirm the task board's position from perception data to increase accuracy.

## Quick Start Guide for this solution

- Clone our repository 
- Compile using `catkin_make`

### Running the solution
Open 4 terminals and source workspace. Run in the 4 terminals
```
roslaunch panda_moveit_config pc_control_moveit_rviz.launch
```
```
rostopic pub -r 10 /franka_control/error_recovery/goal franka_msgs/ErrorRecoveryActionGoal "{}"
```
```
rosrun perception perception.py
```
```
rosrun central central_controller
```

- **`roslaunch panda_moveit_config pc_control_moveit_rviz.launch`** launches the controllers, RViz and MoveIt for the Panda arm using our custom configuration that includes the camera and a custom panda_moveit_config package
- **`rostopic pub -r 10 /franka_control/error_recovery/goal franka_msgs/ErrorRecoveryActionGoal "{}"`** recovers from errors and reflexes that might occur during the execution at 10 Hz
- **`rosrun perception perception.py`** runs our perception node
- **`rosrun central central_controller`** runs our central processing (movements, planning, logic, etc.)
