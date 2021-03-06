# widowx_arm_dev

ROS support for WidowX including MoveIt!, IKFast, Pick & Place / Sorting demo, and Gazebo support.

Optionally using SR300 for pointcloud.

Depending on kbogert/arbotix_ros/turtlebot2i [branch](https://github.com/kbogert/arbotix_ros/tree/turtlebot2i) for gripper controller.

## Quick Start:

mkdir -p ~/widowx_arm/src

cd ~/widowx_arm/src

git clone https://github.com/kbogert/widowx_arm.git .

git clone https://github.com/kbogert/arbotix_ros.git -b turtlebot2i

cd ~/widowx_arm

catkin_make

source devel/setup.bash

roslaunch widowx_arm_bringup arm_moveit.launch sim:=false sr300:=false

## Object manipluation:

roslaunch widowx_arm_bringup arm_moveit.launch sim:=false sr300:=true

roslaunch widowx_block_manipulation block_sorting_demo.launch

## Simulating the WidowX arm in Gazebo

Requires installation of the University of Patras Robotics Group Gazebo mimic joint plugin (clone the package: https://github.com/roboticsgroup/roboticsgroup_gazebo_plugins , compile with catkin_make)

roslaunch widowx_arm_gazebo widowx_arm.launch

roslaunch widowx_arm_moveit_config widowx_arm_moveit_gazebo.launch

