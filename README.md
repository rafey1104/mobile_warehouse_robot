# Warehouse Robot Simulation with ROS 2 and Gazebo

This project simulates a warehouse robot using ROS 2 and Gazebo. It includes a custom-built robot model, a warehouse environment, and ROS 2 nodes for robot control and navigation.

## Table of Contents

- [Real-World Applications](#real-world-applications)
- [Prerequisites](#prerequisites)
- [Build the Warehouse Robot](#build-the-warehouse-robot)
- [Integrate ROS 2 and Gazebo](#integrate-ros-2-and-gazebo)
- [Build a Warehouse](#build-a-warehouse)
- [Launch Your Robot and Warehouse Using ROS 2](#launch-your-robot-and-warehouse-using-ros-2)
- [Move the Robot Around the Warehouse](#move-the-robot-around-the-warehouse)

## Real-World Applications

This simulation project demonstrates the potential for autonomous robots in warehouse operations, showcasing:

- Efficient inventory management
- Automated order fulfillment
- Enhanced workplace safety
- Optimized space utilization

## Prerequisites

- ROS 2 Foxy or later
- Gazebo 11 or later
- `ros-foxy-gazebo-ros-pkgs`

## Build the Warehouse Robot

1. Create `model.config` file
2. Download mesh files
3. Create `model.sdf` file
4. Test your robot in Gazebo

## Integrate ROS 2 and Gazebo

Install the necessary packages:

```bash
sudo apt install ros-foxy-gazebo-ros-pkgs
```

## Build a warehouse

Return to the root of your workspace:

```bash
colcon build --packages-select warehouse_robot_controller_pkg
```

## Launch Your Robot and Warehouse Using ROS 2

```bash
ros2 launch warehouse_robot_spawner_pkg gazebo_world.launch.py
```

Open a new terminal window, and launch the controller.

```bash
ros2 launch warehouse_robot_controller_pkg controller_estimator.launch.py
```

## Move the Robot Around the Warehouse

Open a new terminal window, and type:

```bash
ros2 launch warehouse_robot_spawner_pkg gazebo_world.launch.py
```

Then open another terminal window, and type:

```bash
ros2 run turtlebot3_teleop teleop_keyboard --ros-args --remap /cmd_vel:=/demo/cmd_vel
```
