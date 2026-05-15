
# UR10 Pick and Place

Autonomous Pick-and-Place system using UR10 robot, ROS2 Humble, OAK-D Camera, and Robotiq 3F gripper with visual servoing and color-based object detection.

---

## Features

- Real-time visual servoing
- Color-based object tracking
- OAK-D RGB camera integration
- Robotiq 3F gripper control
- Automatic pick-and-place
- Voice command support
- Collision-aware object selection
- HSV object selection using mouse click
- ROS2 Humble compatible
- UR10 RTDE control

---

## System Overview

This project performs autonomous object detection and pick-and-place using visual feedback from an OAK-D camera mounted on the robot end-effector.

The robot:
1. Detects object
2. Aligns gripper with object orientation
3. Picks object
4. Places object at predefined location
5. Returns to search pose

---

## Hardware Used

- UR10 Robot
- OAK-D Pro Camera
- Robotiq 3F Gripper
- Ubuntu 22.04
- ROS2 Humble

---

## Software Stack

- ROS2 Humble
- Python
- OpenCV
- RTDE Control
- NumPy
- CvBridge

---

## Repository Structure

```bash
Pick-Place-Simulation/
│
├── src/
├── images/
├── videos/
├── vision_servoing.py
├── README.md
```

---

## Installation

### Clone Repository

```bash
git clone https://github.com/Pankaj036/Pick-Place-Simulation.git
```

---

### Build Workspace

```bash
cd ~/ur_ws
colcon build
source install/setup.bash
```

---

## Run the Node

```bash
ros2 run ur10_visual_pick vision_servoing
```

---

## Camera Topic

```bash
/oak/rgb/image_raw
```

---

## Robot Configuration

```python
Robot IP : 192.168.1.102
Gripper IP : 192.168.1.105
```

---

## Object Selection

### Mouse Selection
- Left Click → Select object color
- Right Click → Clear selection

### Voice Commands
Supported:
- pick blue object
- pick red object
- pause
- resume
- clear

---

## Visual Servoing

The robot continuously aligns itself with the object center using image-based feedback.

Features:
- Dynamic center alignment
- HSV-based segmentation
- Contour filtering
- Object orientation estimation
- Wrist alignment

---

## Pick and Place Workflow

1. Detect target object
2. Align TCP orientation
3. Move to pick position
4. Close gripper
5. Lift object
6. Move to place position
7. Release object
8. Return to search pose

---

## Safety Features

- Tracking pause after placement
- Gripper self-chasing prevention
- Object-held detection
- Exclusion zone for gripper visibility

---

## Demo Images

## RViz
![RViz](images/rviz.png)

## Gazebo
![Gazebo](images/gazebo.png)

## Pick and Place
![PickPlace](images/pickplace.png)

---

## Demo Video

Add your video link here:

```text
https://youtube.com/
```

---

## Future Improvements

- YOLOv8 object detection
- Depth estimation
- MoveIt2 planning
- Multi-object sorting
- Reinforcement learning
- VLA training pipeline

---

## Author

Pankaj Shelar

---

## License

MIT License
