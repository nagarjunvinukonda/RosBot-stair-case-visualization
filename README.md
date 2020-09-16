# RosBot-stair-case-visualization
Visualizing stair case using Laser scan in gazebo environment using ROS turtlebot

The rosbot_description contains a dedicated readme for its operation. Just place it in the ROS workspace in the src folder and catkin_make. 

The stairs is a custom environment build for the functionality to add stairs in the environment hence, it should be added to .gazebo -> models folder and you can add it directly in gazebo empty world and use laser scan and pointcloud2 functionality.

Use this to run the overall package with laserscan and PCL2 data
roslaunch rosbot_description rosbot_rviz_amcl.launch
