# Manipulator Mounted Mobile Robot

### Stage 1: Design
Design of the robot was done on Fusion360 and preliminary URDF and gazebo files generated using fusion2urdf plugin.
ROS Noetic, Gazebo 11 and Python3 were used throughout the development of this project.

- The design of the entire bot was divided in 2 phases, first design of the manipulator and then the 4 wheel drive robot. The manipulator was designed as a 6 DOF (revolute joints) robotic arm with a gripper as an end-effector.

![Manipulator](/assets/images/gazebo_image_2.jpg)

- Next a simple 4-wheel drive robot was designed with a fixed link on top for a simple laser range sensor. Two manipulator arms would be mounted on top of the mobile robot.

![Mobile_Robot](/assets/images/gazebo_image_1.jpg)

### Stage 2: Manipulator Control

Moveit configuration packages were generated using Moveit setup assistant with the following specifications:

1. Both grippers were set up as end effectors

![Gripper](/assets/images/rviz_image_2.png)

2. Joint position controllers for each of the arms using KDL kinematics solver

![Joint_controllers](/assets/images/rviz_image_1.png)

3. Commands can be given to move_group using either Rviz GUI, Python scripts or C++ programs.

![Commands](/assets/images/rviz_image_3.png)

### Stage 3: Movement and Navigation
1. cmd_vel is being published which can be used to move the robot either with teleoperation or by publishing directly to topic using nodes.

2. Goal positions can be passed to move_base node for autonomous navigation of the robot.
 
### Further Progress:
- Create a world and objects to test out grasping and manipulation
- Create an entire scenario to test our robot controls and planners.