# **Lab Automation**

## **Overview**
In this project, the robot will transfer a lab vial from one holder to another.

## **Parts**
| **Part** | **Description/Image** |
|---|---|
| [Robot mounting parts](https://github.com/dorna-robotics/education/blob/main/mount_robot/README.md#parts) |   |
| [Gripper mounting parts](https://github.com/dorna-robotics/education/blob/main/attach_two_finger_pneumatic_gripper/README.md#parts) |   |
| [2 x Lab vial holders](https://github.com/dorna-robotics/education/blob/main/lab_automation/Asset/Vial%20Holder%20v10.stl) | <img src="https://i.imgur.com/MbY7aJw.jpeg" alt="Lab Vial Holder" width="100"/> |
| [Lab vials](https://www.amazon.com/dp/B0C8CVQK46?ref=cm_sw_r_cp_ud_dp_GB0VGHMMAQMXRGTBVY2K&ref_=cm_sw_r_cp_ud_dp_GB0VGHMMAQMXRGTBVY2K&social_share=cm_sw_r_cp_ud_dp_GB0VGHMMAQMXRGTBVY2K&skipTwisterOG=2&th=1) | <img src="https://i.imgur.com/iZYnaa3.jpeg" alt="Lab Vials" width="100"/> |
| [1 x Set of pneumatic gripper fingers](https://github.com/dorna-robotics/education/blob/main/lab_automation/Asset/Gripper%20Finger%20v27.stl) | <img src="https://i.imgur.com/eIwONke.jpeg" alt="Pneumatic Gripper Fingers" width="100"/> |
| [8 x M3 8mm screws](https://www.mcmaster.com/91290A113/) |   |

## **Assembly instructions**

1. **Mount the robot**  
   Follow the [robot mounting instructions](https://github.com/dorna-robotics/education/blob/main/mount_robot/README.md#assembly).

2. **Mount the gripper**  
   Follow the [gripper mounting instructions](https://github.com/dorna-robotics/education/blob/main/attach_two_finger_pneumatic_gripper/README.md#assembly).

3. **Attach the pneumatic gripper fingers**  
   Secure the gripper fingers to the gripper using 4 M3 8mm screws.  
   <img src="https://i.imgur.com/qICma2g.jpeg" alt="Pneumatic Gripper Fingers Attached" width="400"/>

4. **Attach the lab vial holders**  
   Fix the lab vial holders to the base plate at the positions (A8, B9, D8, E9).  
   <img src="https://i.imgur.com/rmLVyGH.jpeg" alt="Lab Vial Holders Mounted" height="300" width="400"/>  
   <img src="https://i.imgur.com/gDl34yZ.jpeg" alt="Lab Vial Holders Mounted" height="300" width="400"/>

5. **Complete the assembly**  
   Your assembly is complete!  
   <img src="https://i.imgur.com/9lVQlcO.jpeg" alt="Completed Assembly" width="400"/>

## **Code**
To run the code, use the .ipynb file in this folder. This section explains how the code works:

1. Determine the positions of all lab vial holder cells relative to the robot. Measure the distances between A1 and D1, as well as A1 and A6. Use these measurements to calculate the positions of all cells.

2. Prompt the user to input the holder cell from which they want to pick a vial and the cell where they want to place it.

3. Validate the inputs and convert the positions to Cartesian coordinates for the robot to use.

4. Use the Dorna pick and place function to complete the motion.
