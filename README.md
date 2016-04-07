# COMSE 6731 HUMANOID ROBOTS, SPRING 2016
# Columbia University


## Installation
Everything you need has already been installed on the CLIC lab machines.  If you are trying to install it on your own machine, please follow the instructions here:
http://sdk.rethinkrobotics.com/wiki/Simulator_Installation

## Getting Started

The following lines will not work unless ROS is properly installed.  You can find instructions for how to do this from the ros_tutorial pdf on the class website.

```bash
$ cd ~
$ git clone git@github.com:HumanoidRobotics/baxter_example_code.git
$ cd baxter_example_code
$ source /opt/ros/indigo/setup.bash
$ catkin_make
$ source devel/setup.bash
```

Running the Demo code
-------------------------
First, bring up Gazebo, and Baxter
```bash
$  ./baxter.sh sim
$ roslaunch system_launch everything.launch
```

Then run the individual demos with any of the following:
```bash
$ source devel/setup.bash
$ ./baxter.sh sim
Then:
$ rosrun baxter_examples joint_position_keyboard.py
$ rosrun baxter_examples joint_velocity_wobbler.py
```

Using Moveit!
-------------
Start by bringing up Gazebo and Baxter as in the previous step.
Then, in a new terminal run the following: 
```bash
$ source devel/setup.bash
$ ./baxter.sh sim
$ rosrun baxter_tools enable_robot.py -e
$ rosrun baxter_interface joint_trajectory_action_server.py
```
This will make sure that the robot (simulator) is enabled and can be talked to,
and will also spin up a special node for moving the simulated robot.

In a 3rd terminal run this: 
```bash
$ source devel/setup.bash
$ ./baxter.sh sim
$ roslaunch baxter_moveit_config baxter_grippers.launch
```
This actually launches moveit.


Note: For every new terminal you open up, you will have to run the following:
```bash
$ source devel/setup.bash
$ ./baxter.sh sim
```
