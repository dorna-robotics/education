# **Number Sorting**

## **Overview**
In this project, you'll use the Dorna TA robotic arm and 3d vision system to detect numbered chips within a defined area and sort them according to their numbers.

## **Parts**
| **Part** | **Description/Image** |
|---|---|
| [Robot mounting parts](https://github.com/dorna-robotics/education/blob/main/mount_robot/README.md#parts) |   |
| [Suction gripper mounting parts](https://github.com/dorna-robotics/education/tree/main/attach_suction_gripper#parts) |   |
| 1 x Chip holder/board | <img src="https://i.imgur.com/jwiwhX6.png" alt="Chip Holder/Board" width="100"/> |
| 1 x Set of chips | <img src="https://i.imgur.com/T4xyPR6.png" alt="Set of Chips" width="100"/> |
| [3 x M3 8mm screws](https://www.mcmaster.com/91290A113/) | <img src="https://www.mcmaster.com/mvD/Contents/gfx/ImageCache/912/91290A113_720ffa0a-507b-416c-b5af-22ad90d45eee@4x_638090342177822562.png?ver=ImageNotFound" alt="Set of Chips" width="100"/>  |

## **Assembly instructions**

1. **Mount the robot**  
   Follow the [robot mounting instructions](https://github.com/dorna-robotics/education/blob/main/mount_robot/README.md#assembly).

2. **Attach the suction gripper**  
   Follow the [suction gripper mounting instructions](https://github.com/dorna-robotics/education/tree/main/attach_suction_gripper#assembly).

3. **Attach the chip holder/board**  
   Secure the chip holder/board to the holes at positions (A7, C7, and E7) using 3 M3 8mm screws.  
   <img src="img_here" alt="Chip Holder/Board Attached" height="300" width="400"/>  
   <img src="img_link_here" alt="Chip Holder/Board Attached" height="300" width="400"/>

4. **Place the numbered chips**  
   Position the numbered chips in the designated area on the chip holder/board.  
   <img src="img_link_here" alt="Numbered Chips Placed" height="300" width="400"/>

5. **Complete the assembly**  
   Your assembly is complete!  
   <img src="img_here" alt="Completed Assembly" width="400"/>

## **Code**
To run the code, use the [.ipynb file](https://github.com/dorna-robotics/education/blob/main/ml_object_detection/number_sorting.ipynb) in this folder. This section explains how the code works:

1. The robot retrieves the position of the object (via the camera) and its associated class (the object's number).

2. The robot then calculates the appropriate placement location based on the object's number.

3. A pick-and-place operation is executed, where the robot picks the object, moves to the middle position, and finally places the object in its designated location.

4. After placing, the robot returns to the imaging position to detect the next object.

5. This loop runs for a predefined number of objects (in this case, 5), performing the sorting task for each detected item.
