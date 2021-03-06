# rosbot_description #

URDF model for Gazebo integrated with ROS.

## Installation. ## 

We assume that you are working on Ubuntu 16.04 and already have installed ROS Kinetic. If not, follow the [ROS install guide](http://wiki.ros.org/kinetic/Installation/Ubuntu)

Prepare the repository:
```
cd ~
mkdir ros_workspace
mkdir ros_workspace/src
cd ~/ros_workspace/src
catkin_init_workspace
cd ~/ros_workspace
catkin_make
```

Above commands should execute without any warnings or errors.


Clone this repository to your workspace:

```
cd ~/ros_workspace/src
git clone https://github.com/husarion/rosbot_description.git
```

Install depencencies:

```
cd ~/ros_workspace
rosdep install --from-paths src --ignore-src -r -y
```

Build the workspace:

```
cd ~/ros_workspace
catkin_make
```

From this moment you can use rosbot simulations. Please remember that each time, when you open new terminal window, you will need to load system variables:

```
source ~/ros_workspace/devel/setup.sh
```

## How to use ##

### Creating, saving and loading the Map ###

Run the following commands below. Use the teleop to move the robot around to create an accurate and thorough map.

In Terminal 1, launch the Gazebo simulation:

```
roslaunch rosbot_description rosbot_rviz_gmapping.launch
```

In Terminal 2, start teleop and drive the ROSbot, observe in Rviz as the map is created:

```
roslaunch rosbot_navigation rosbot_teleop.launch
```

When you are satisfied with created map, you can save it. Open new terminal and save the map to some given path: 

```
rosrun map_server map_saver -f ~/ros_workspace/src/rosbot_description/src/rosbot_navigation/maps/test_map
```

Now to make saved map loading possible you have to close all previous terminals and run the following commands below. Once loaded, use rviz to set 2D Nav Goal and the robot will autonomously reach the indicated position

In Terminal 1, launch the Gazebo simulation

```
roslaunch rosbot_description rosbot_rviz_amcl.launch
```


