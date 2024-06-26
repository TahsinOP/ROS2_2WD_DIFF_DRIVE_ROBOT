# Project Goal
The project aims to develop a two-wheeled differential drive robot controlled using ROS 2. The robot is designed to be controlled via keyboard teleoperation, where key inputs are mapped to specific robot movements. The project also explores the implementation of a PID controller for motor control, enabling smoother and more precise movement. Additionally, the project lays the foundation for future enhancements, such as integrating SLAM (Simultaneous Localization and Mapping), computer vision, and AI applications

# Tech Stack 

![ROS Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bb/Ros_logo.svg/85px-Ros_logo.svg.png)  ![Arduino Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/8/87/Arduino_Logo.svg/85px-Arduino_Logo.svg.png)  ![Raspberry Pi Logo](https://upload.wikimedia.org/wikipedia/en/thumb/c/cb/Raspberry_Pi_Logo.svg/50px-Raspberry_Pi_Logo.svg.png)

# Introduction
The robot operates on a differential drive system, which consists of two independently driven wheels. By controlling the speed and direction of each wheel, the robot can move in various directions, including forward, backward, left, and right. The use of ROS 2 provides a modular and scalable framework for developing and controlling robotic systems, facilitating integration with sensors, actuators, and higher-level algorithms. 

The project involves a simple simulation on Gazebo but the major focus is on building real-time working DIY robot using minimal hardware cost. It also emphasises the power,speed,accuracy and low-latency response of ROS2 middleware communication interfaced with Arduino through serial communication seamlessly .

# Hardware
## Prototype - 1 
- Two DC motors connected to an L298N motor driver for motor control.
- Castor wheel (1) + Rubber Wheels (2)
- 3-D Printed Acrylic Body 
- 12V Supply (Power Bank)
- 7V supply for motors and L298N 
- 12V Supply (Power Bank)
- Arduino board for interfacing with the motor driver and serial communication with the Raspberry Pi.
- Encoders (optional) for providing feedback on wheel positions.

 ![photo_2024-04-20_12-47-36](https://github.com/TahsinOP/ROS2_2WD_DIFF_DRIVE_ROBOT/assets/117567813/2277b17b-51e7-49d3-bb7e-872446deea83)

## Prototype - 2 ( Better Performance ) 
- Two DC motors connected to arduino motor shield
- Castor wheel (1) + Rubber Wheels (2)
- 3-D Printed Acrylic Body
- 12V Main power Supply (Power Bank)
- Arduino Uno , Raspberry Pi 4
  


# Workflow 

![ROS2_controlled_teleoperation drawio (1)](https://github.com/TahsinOP/ROS2_2WD_DIFF_DRIVE_ROBOT/assets/117567813/0fb5b0b3-2b1a-4344-8918-5cb9a7c15457)

1. **Setup and Configuration:**
   - ROS 2 running on both host-machine and the Raspberry Pi on a network.
   - Pi accesed remotely using `ssh pi@ip_address`
   - Configured the Arduino for serial communication (UART) with the Raspberry Pi.
   
2. **Teleoperation Node:**
   - Develop a ROS 2 node on the host-PC for keyboard teleoperation.
   - Map keyboard inputs (WASD) to robot commands (Forward, Left, Backward, Right, Stop).
   - Publish robot commands to the `robot_commands` topic.
   
3. **Serial Communication Node:**
   - Create a ROS 2 node on the Raspberry Pi to subscribe to the `robot_commands` topic.
   - Receive robot commands and transmit them to the Arduino via serial communication.

4. **Arduino Code:**
   - Implement Arduino code to interpret serial commands and control the motors accordingly.
   - Optionally, integrate a PID controller for smoother motor control using encoder feedback (if available).
  
# Demonstration 
## Robot Navigation 
https://github.com/TahsinOP/ROS2_2WD_DIFF_DRIVE_ROBOT/assets/117567813/7a7cd655-20f8-4538-b09f-8474f4065880

## ROS2 Interface




     
# Applications
- Educational purposes: Provides a hands-on learning experience for understanding robotics, ROS 2, and PID control.
- Research and prototyping: Enables rapid prototyping and experimentation with robotic systems.
- Hobby projects: Offers enthusiasts the opportunity to build and customize their own robot platforms for various applications.

# Improvements: Adding SLAM, Computer Vision, and AI Applications
1. **SLAM (Simultaneous Localization and Mapping):**
   - Integrate SLAM algorithms to enable the robot to map its environment and localize itself within it.
   - Use sensors such as LiDAR or depth cameras for environment perception.

2. **Computer Vision:**
   - Implement computer vision algorithms for object detection, tracking, and recognition.
   - Utilize cameras mounted on the robot for visual perception tasks.

3. **AI Applications:**
   - Explore AI techniques for autonomous navigation and decision-making.
   - Develop reinforcement learning algorithms for adaptive and self-improving robot behaviors.

By incorporating these enhancements, the robot can become more autonomous and capable of performing complex tasks in dynamic environments. These improvements open up possibilities for applications in areas such as autonomous mobile robots, robotic exploration, and human-robot interaction.
