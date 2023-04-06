# UR5e Gazebo joint velocity controller package with ros_control

This package provides simulated velocity control of a UR5e in Gazebo.
I surprisingly couldn't find an existing solution for this.
This package is based heavily on the [roboticscasual blog post here](https://roboticscasual.com/ros-tutorial-control-the-ur5-robot-with-ros_control-tuning-a-pid-controller/), which implemented position control.

## Requirements
Tested on ROS Noetic.
Requires the `ur-description` package, which provides robot descriptions for UR manipulators.

## Usage
Simply run
```
roslaunch ur5e-joint-velocity-control ur5e_gazebo_joint_velocity_control.launch
```
to launch a Gazebo interface with the UR5e loaded.

Errors about setting PID gains can be safely avoided. [They aren't necessary for](https://www.rosroboticslearning.com/ros-control) `JointVelocityController`s, so I'm not sure why I'm seeing angry red text.

Issue commands to the `joint_group_vel_controller/command` topic. It accepts `Float64MultiArray` messages.
