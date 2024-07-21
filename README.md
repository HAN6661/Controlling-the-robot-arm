# Controlling-the-robot-arm

## Controlling the robot arm by joint state publisher
### installed catkin and sourced your environment.
```
source /opt/ros/noetic/setup.bash
```
### Create and build a catkin workspace:
```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
```
### Then
```
 source devel/setup.bash
```
```
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
```
### Add the “arduino_robot_arm” package to “src” folder
```
cd ~/catkin_ws/src
sudo apt install git
git clone https://github.com/smart-methods/arduino_robot_arm 
```
### Install all the dependencies 
```
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src -r -y
sudo apt-get install ros-noetic-moveit
sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
```

### Compile the package
```
catkin_make
```

## Controlling the motors
```
roslaunch robot_arm_pkg check_motors.launch

```
![Screenshot from 2024-07-14 23-33-45](https://github.com/user-attachments/assets/e24de598-03c0-4a13-b953-37daf0b4e7d3)

![Screenshot from 2024-07-14 23-33-53](https://github.com/user-attachments/assets/fcce23a5-6a87-4132-9301-973d69c57534)


## Controlling the motors in simulation
```
roslaunch robot_arm_pkg check_motors.launch
roslaunch robot_arm_pkg check_motors_gazebo.launch
rosrun robot_arm_pkg joint_states_to_gazebo.py

```

![Screenshot from 2024-07-14 23-34-51](https://github.com/user-attachments/assets/7edbf136-4e15-42e6-80c9-da437194b4c0)


### You may need to change the permission
```
cd catkin/src/arduino_robot_arm/robot_arm_pkg/scripts
sudo chmod +x joint_states_to_gazebo.py

```
## Controlling the robot arm by Moveit and kinematics
```
roslaunch moveit_pkg demo.launch
```
```
roslaunch moveit_pkg demo_gazebo.launch
```
![Screenshot from 2024-07-14 23-44-19](https://github.com/user-attachments/assets/716590fe-5d84-4b76-9f10-24f0c4d6d96b)

![Screenshot from 2024-07-14 23-55-58](https://github.com/user-attachments/assets/270fd9ae-ef5a-433d-9c68-8d424912b513)


