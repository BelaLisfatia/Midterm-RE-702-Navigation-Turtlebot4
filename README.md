# Case Study
A robot is tasked with delivering goods from Room 203 to the BRAIL Lobby on the 2nd Floor of the Main Building of Batam State Polytechnic. The robot must be capable of autonomous localization, mapping, and navigation using ROS. To simulate the delivery process, use a buzzer indicator with the following conditions:

• When the robot reaches the pick location (Room 203) and "picks up an item," the buzzer indicator sounds once or a sound is heard from the speaker.

• When the robot reaches the place location (BRAIL Lobby) and "delivers an item," the buzzer sounds twice or a sound is heard from the speaker.

# TurtleBot4 Setup

## 1. Create Workspace & Build ROS2 Workspace
### 1. Create Workspace
```bash
mkdir ~/kelompok4b_uts/src
cd ~/kelompok4b_uts/src
```

### 2. Clone GitHub Repository
```bash
https://github.com/BelaLisfatia/Midterm-RE-702-Navigation-Turtlebot4.git
```

### 3. Activated ROS2 Humble Environment
```bash
cd ~/kelompok4b_uts/src
source /opt/ros/humble/setup.bash
```

### 4. Build ROS2 Workspace
```bash
cd ~/kelompok4b_uts
colcon build
```

# Running Instruction

## A. ROS Visualization (RViz)
Please make sure you have installed Ubuntu with Robot Operating System (ROS) and simulation tools (RViz) for better performance to open visualization on your laptop.
Run this command on terminal (if use ROS2 Humble):
```bash
ros2 launch turtlebot4_viz view_robot.launch.py
```

## B. View Map Localization
### 1. Open a new terminal and connect to the robot:
```bash
ssh ubuntu@192.168.185.3
```

### 2. Change directory on your workspace:
```bash
cd ~/kelompok4b_uts
```

### 3. Run localization with your map:
```bash
ros2 launch pose_nav_turtle localization.launch.py map:=src/nav_kel4b/maps/kel4b.yaml
```
### 4. In RViz, use 2D Pose Estimate to set the initial pose of robot

## C. Navigation Package
### 1. Open a new terminal and connect again to the robot:
```bash
ssh ubuntu@192.168.185.3
```

### 2. Change directory on your workspace:
```bash
cd ~/kelompok4b_uts
```

### 3. Launch your navigation package:
```bash
ros2 launch nav_kel4b run_nav.launch.py
```

### 4. Test the navigation using Nav2 Goal in RViz

## D. Node Navigation Task
### 1. Open a new terminal and connect again to the robot:
```bash
ssh ubuntu@192.168.185.3
```

### 2. Change directory on your workspace:
```bash
cd ~/kelompok4b_uts
```

### 3. Run your node of navigation task:
```bash
ros2 run nav_kel4b nav_kel4b
```

Now you have your own ROS2 humble workspace, RViz visualization, localization map, your navigation package, and node navigation task to deliver goods from Room 203 to the BRAIL Lobby.

Robot Demonstration: https://youtu.be/Mq68uBortnk?si=dAGJYUWlQ1hG176A









