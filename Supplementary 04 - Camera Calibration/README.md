# **Camera Calibration**

## **Overview**
This guide describes the camera calibration process for the Dorna TA robotic arm and the Dorna 3D Vision system.

## **Parts**

| **Part** | **Description/Image** |
|---|---|
| [Robot mounting parts](https://github.com/dorna-robotics/education/tree/main/mount_robot#parts) |   |
| [Dorna ArUco](https://github.com/dorna-robotics/education/tree/main/camera_calibration/Assets) | <img src="./Assets/Images/68747470733a2f2f692e696d6775722e636f6d2f375078344f77692e706e67.png" alt="Dorna ArUco" width="100"/> |

## **Assembly instructions**
1. Start by completing [these instructions](https://github.com/dorna-robotics/education/blob/main/camera_calibration/Assets/README.md) to print and assemble the ArUco.
2. Next, mount the Aruco at holes ``9D`` and ``10C``.

## **Code**
To run the code, use the [.ipynb file](https://github.com/dorna-robotics/education/blob/main/camera_calibration/camera_calibration.ipynb) in this folder. This section explains how the code works:

1. Using the camera, the robot captures data about the ArUco marker placed on the calibration plate.

2. The robot’s arm is moved to various predefined positions around the marker, allowing the system to observe how the camera sees the marker from different perspectives. The data collected from the different positions is used to minimize the error between the robot's actual position and what the camera perceives. 

3. Then this data is used to calculate the transformation matrix that links the camera’s coordinate system to the robot’s joint system.

4. An optimization function is applied to refine this matrix, resulting in an accurate representation of the camera's viewpoint in relation to the robot's joints.

## **Wiring Instructions**
1. [Robot Wiring](https://github.com/dorna-robotics/education/tree/main/mount_robot)
