# **Lab Automation**

## **Parts**
| **Part** | **Description/Image** |
|---|---|
| [Robot Mounting Parts](https://github.com/dorna-robotics/education/blob/main/mount_robot/README.md#parts) |   |
| [Gripper Mounting Parts](https://github.com/dorna-robotics/education/blob/main/attach_two_finger_pneumatic_gripper/README.md#parts) |   |
| [2 x Lab Vial Holder](https://github.com/dorna-robotics/education/blob/main/lab_automation/Asset/Vial%20Holder%20v10.stl) | <img src="https://i.imgur.com/MbY7aJw.jpeg" alt="Lab Vial Holder" width="100"/> |
| [Lab Vials](https://www.amazon.com/dp/B0C8CVQK46?ref=cm_sw_r_cp_ud_dp_GB0VGHMMAQMXRGTBVY2K&ref_=cm_sw_r_cp_ud_dp_GB0VGHMMAQMXRGTBVY2K&social_share=cm_sw_r_cp_ud_dp_GB0VGHMMAQMXRGTBVY2K&skipTwisterOG=2&th=1) | <img src="https://i.imgur.com/iZYnaa3.jpeg" alt="Lab Vials" width="100"/> |
| [1 x Set of Pneumatic Gripper Fingers](https://github.com/dorna-robotics/education/blob/main/lab_automation/Asset/Gripper%20Finger%20v27.stl) | <img src="https://i.imgur.com/eIwONke.jpeg" alt="Pneumatic Gripper Fingers" width="100"/> |
| [8 x M3 8mm Screws](https://www.mcmaster.com/91290A113/) |   |

## **Assembly**

 * [Mount the robot.](https://github.com/dorna-robotics/education/blob/main/mount_robot/README.md#assembly)
   
 * [Mount the Gripper.](https://github.com/dorna-robotics/education/blob/main/attach_two_finger_pneumatic_gripper/README.md#assembly)

 * Attach the Pneumatic Gripper Fingers to the Dorna 2 Finger Gripper using 4 of the [M3 8mm Screws](https://www.mcmaster.com/91290A113/).

   <img src="https://i.imgur.com/qICma2g.jpeg" alt="Dorna" width ="400"/>

 * Attach the Lab Vial Holders to the Dorna Base Plate to the holes in position (A8, B9 and D8, E9)

   <img src="https://i.imgur.com/rmLVyGH.jpeg" alt="Dorna" Height ="300" Width="400"/>
   <img src="https://i.imgur.com/gDl34yZ.jpeg" alt="Dorna" Height ="300" Width="400"/>

* Your Assembly Is Done!
  
   <img src="https://i.imgur.com/9lVQlcO.jpeg" alt="Dorna" width ="400"/>

## **Code**
To run the code you will need to use the .ipynb file in this folder. This section is where you will find an explanation of how the code works.

 1. The first thing we need to determine the positions of all of the Lab Vial Holder Cells Relative to the Robot. To do this, we will messure the distances between A1 and D1, as well as the distance between A1 and A6. Using these distances we will calculate the position of all of the cells.
 2. The next thing we will do is prompt and gather input from the user for what holder cell they want to pick the vial from and what cell they want to place it in.
 3. We will then check to make sure these inputs are valid, following this we will covert these postions to cartesian coordinates for the robot to use.
 4. Finally, we use the Dorna Pick and Place function to complete the motion.
