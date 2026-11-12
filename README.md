# 4-DOF Industrial Robotic Arm – ROS 2

![3D MODEL](dimages/Interface.png)

A 4-degree-of-freedom (4-DOF) robotic arm designed in **Fusion 360** and integrated with **ROS 2 Jazzy** using URDF/Xacro. This project demonstrates robot description modeling, link and joint configuration, 3D mesh integration, joint state visualization, and TF frame verification in RViz2.

## Project Overview

The robotic arm consists of four revolute joints that provide rotational movement across its links. The mechanical model was designed in Fusion 360, exported as STL mesh files, and integrated into ROS 2 through a Xacro-based robot description.

The robot can be visualized in RViz2, and its joint movements can be controlled using the Joint State Publisher GUI.

## Features

- 4-DOF robotic arm model designed in Fusion 360.
- URDF/Xacro-based robot description.
- Custom STL meshes for robot links.
- Four revolute joints with configured axes and joint limits.
- Visual and collision geometry definitions.
- Joint state control using Joint State Publisher GUI.
- Robot visualization using RViz2.
- TF frame publishing and verification using `tf2_tools`.

## Technologies Used

- ROS 2 Jazzy
- URDF
- Xacro
- RViz2
- Joint State Publisher GUI
- Robot State Publisher
- TF2
- Fusion 360
- Ubuntu 24.04

## Project Structure

```text
industrial_arm_description/
├── launch/
│   └── display.launch.py
├── meshes/
│   ├── base_link_1.stl
│   ├── link1_1.stl
│   ├── s_link1_1.stl
│   ├── s_link2_1.stl
│   ├── link2_1.stl
│   ├── s_link3_1.stl
│   └── end_effector.stl
├── urdf/
│   ├── 4dof_arm.xacro
│   ├── materials.xacro
│   └── fusion2urdf.txt
├── rviz/
├── CMakeLists.txt
└── package.xml
```

## Requirements

- Ubuntu 24.04
- ROS 2 Jazzy
- Xacro
- RViz2
- Robot State Publisher
- Joint State Publisher GUI
- TF2 tools

Install the required ROS 2 packages:

```bash
sudo apt update
sudo apt install ros-jazzy-xacro \
ros-jazzy-rviz2 \
ros-jazzy-robot-state-publisher \
ros-jazzy-joint-state-publisher-gui \
ros-jazzy-tf2-tools
```

## Installation and Setup

Create a ROS 2 workspace if you do not already have one:

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
```

Clone this repository:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

Build the package:

```bash
cd ~/ros2_ws
colcon build --packages-select industrial_arm_description
```

Source the workspace:

```bash
source ~/ros2_ws/install/setup.bash
```

## Launch the Robot

Run the following command to launch the robotic arm visualization:

```bash
ros2 launch industrial_arm_description display.launch.py
```

This launches:

- Robot State Publisher
- Joint State Publisher GUI
- RViz2

The robot model can be viewed in RViz2, and the joint sliders can be used to change the arm configuration.

## TF Frame Verification

To generate a TF frame diagram, run:

```bash
ros2 run tf2_tools view_frames
```

This generates a PDF containing the robot's TF frame hierarchy.

To inspect the available TF frames:

```bash
ros2 run tf2_tools view_frames
```

## Learning Outcomes

- Understanding robot modeling using URDF and Xacro.
- Defining links, joints, axes, and joint limits.
- Integrating Fusion 360 mesh models into ROS 2.
- Visualizing robot models using RViz2.
- Understanding robot state publishing and TF frame relationships.

## Future Improvements

- Add forward and inverse kinematics.
- Implement trajectory control.
- Integrate MoveIt 2 for motion planning.
- Test the robot with physical hardware.

## Author

**Aswin S Pillai**

B.Tech – Robotics and Artificial Intelligence

## License

This project is intended for educational and academic purposes. Add a suitable open-source license before permitting reuse or redistribution.
