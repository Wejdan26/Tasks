# Tasks

.....................

Task 1:

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

Task 2

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








