# Tasks

.....................

Task1:

..How to install Ros on ubuntu..

1/Installation:

1.1/ Configure your Ubuntu repositories

Configure your Ubuntu repositories to allow "restricted," "universe," and "multiverse."

1.2/ Setup your sources.list

$sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

1.3/ Set up your keys

$sudo apt install curl # if you haven't already installed curl curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

1.4/ Installation

$sudo apt update

Desktop-Full Install:

$sudo apt install ros-noetic-desktop-full

1.5/ Environment setup

$source /opt/ros/noetic/setup.bash

...............................................................................................................................

Task3:

..Install-robot-arm..

$sudo apt-get install ros-noetic-catkin

$mkdir -p ~/catkin_ws/src

$cd ~/catkin_ws/

$catkin_make

$cd ~/catkin_ws/src

$git clone https://github.com/smart-methods/arduino_robot_arm.git 

$cd ~/catkin_ws

$rosdep install --from-paths src --ignore-src -r -y

$sudo apt-get install ros-kinetic-moveit

$sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui

$sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher

$sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control

$sudo nano ~/.bashrc

End of the (bashrc) file add the follwing line
(source /home/wesam/catkin_ws/devel/setup.bash)
then 
ctrl + o

$source ~/.bashrc

$roslaunch robot_arm_pkg check_motors.launch

............................................................................................................................

Task 4:

..Configuring Arduino with ROS..

Install Arduino IDE in Ubuntu https://www.arduino.cc/en/software 

to install run $ sudo ./install.sh after unzipping the folder

Install the arduino package and ros library http://wiki.ros.org/rosserial_arduino/Tutorials/Arduino%20IDE%20Setup

Make sure to change the port permission before uploading the Arduino code $ sudo chmod 777 /dev/ttyUSB0

Controlling the robot arm by joint_state_publisher

$ roslaunch robot_arm_pkg check_motors.launch

connect with hardware by running:

$ rosrun rosserial_python serial_node.py _port:=/dev/ttyUSB0 _baud:=115200

Simulation

$ roslaunch robot_arm_pkg check_motors.launch

$ roslaunch robot_arm_pkg check_motors_gazebo.launch

$ rosrun robot_arm_pkg joint_states_to_gazebo.py

$ sudo chmod +x ~/catkin_ws/src/arduino_robot_arm/robot_arm_pkg/scripts/joint_states_to_gazebo.py

$ roslaunch moveit_pkg demo.launch

connect with hardware by running:

$ rosrun rosserial_python serial_node.py _port:=/dev/ttyUSB0 _baud:=115200

Simulation

$ roslaunch moveit_pkg demo_gazebo.launch








