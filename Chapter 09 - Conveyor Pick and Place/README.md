# **Conveyor Pick and Place**

## **Overview**
In this project, we wish to implement a simple robotic system incorporating input and outputs to accomplish a simple pick-and-place task on a controllable conveyor belt. You will follow the step-by-step instructions to program the robot to control the conveyor based on the proximity sensor’s data and to move around objects on the conveyor using a pneumatic gripper. This practice is similar to many real scenarios in the industry such as packaging and assembly tasks.

The input device is a proximity sensor that activates whenever it senses the presence of an object in proximity to it. On the other hand, the output system is a conveyor belt, and we can control its motor using the controller’s digital output pins. 

At the end of this project, small boxes are moved using the conveyor. Whenever they reach the end of the conveyor, it stops. The robot picks up that box using the gripper and moves it to the front of the conveyor, and the conveyor starts moving again, and the loop continues.


## **Parts**
| **Part** | **Description/Image** |
|:---|---|
| [Robot mounting parts](https://github.com/dorna-robotics/education/tree/main/mount_robot#parts) |  <img src="./images/fig1.jpg" alt="Dorna robot" width="200"/>  |
| [Robot pneumatic gripper]() | <img src="./images/fig2.jpg" alt="Pneumatic Gripper" width="200"/>   |
| [2 x Base plate connectors](https://dorna.ai/) | <img src="./images/fig3.jpg" alt="Base Plate Connectors" width="200"/> |
| Proximity sensor | <img src="./images/fig4.jpg" alt="Proximity sensor" width="200"/> |
| Small Conveyor Belt| <img src="./images/fig5.jpg" alt="Conveyor belt" width="200"/>| 
|Conveyor Belt Mounting Brackets (also sensor mount)| <img src="./images/fig6.jpg" alt="Conveyor mounting brackets" width="200"/>| 
|Dorna two Mounting Plate Adapter/Bracket| <img src="./images/fig7.jpg" alt="Robot's mounting plate" width="200"/>| 

## **Assembly instructions**


1. **Wiring Conveyor Belt**
    Start by detaching the motor from the conveyor belt, this can be done by removing the 4 bolts on the front of the belt’s chassis.

<img src="./images/fig8.jpg"  width="400"/>   

Solder an 18-gauge wire to both the power and ground terminals on the motor. Solder the red and black to the same terminals shown below.

<img src="./images/fig9.jpg"  width="400"/>   

   
Reattach the motor. Then, using the green terminals on the front of Dorna's control box, connect the Red to the 24v and the black to one of the output connections (in this case, 1 was used). Here we can also observe how the proximity sensor has also been attached to the controller as an input device (here it is input 6)

<img src="./images/fig10.jpg"  width="400"/>   

Plese follow the indictation below for the connections of wire of the input and output systems in this project:

<img src="./images/wire-colors.jpg" />   

Now the belt is connected and it can be controlled via the output system of the robot. 

2. **Mounting Conveyor Belt**
   First, use the four black M5 bolts to attach the conveyor mounting brackets to the Aluminum Mounting Plate.

<img src="./images/fig11.jpg"  width="400"/>   


Then, use the four black M3 bolts and the M3 nuts to mount the conveyor belt to its mounting brackets.

<img src="./images/fig12.jpg"  width="600"/>   

3. **Mounting Sensor**
Mount the Infrared Sensor to the left conveyor mounting bracket through the hole on the bracket and plastic nuts on the sensor. Pay special attention to aligning the sensor at the edge of the conveyor belt to get the most accurate readings.

<img src="./images/fig13.jpg"  width="400"/>   
 

4. **Mount the robots**   
   Follow the [mounting instructions](https://github.com/dorna-robotics/education/tree/main/mount_robot#assembly) instructions to prepare the robot. To mount the robot on the plates, start by pressing the four M8 nuts into the hexagonal holes on the bottom of the Dorna to Mounting Plate Adapter.

<img src="./images/fig14.jpg"  width="400"/>   
<img src="./images/fig15.jpg"  width="400"/>   


   Using the four black M8 bolts attach the Dorna 2 to the Mounting Plate Adapter. Using the four silver M5 bolts attach the mounting plate adapter to the aluminum mounting plate. 

<img src="./images/fig16.jpg"  width="400"/>   

5. **Attach the pneumatic gripper**  
   Attach the pneumatic grippers to the robot following the #proper link. Install the Jaws on the gripper.
   
<img src="./images/fig17.jpg"  width="400"/>   

Attach the tubing to the solenoid valve. 

<img src="./images/fig18.jpg"  width="400"/>   
   
Run one tube from the solenoid valve to the compressor.

<img src="./images/fig19.jpg"  width="400"/>   

We should also connect the solenoid wires to the controller as another output device (here we have used output 7) just like below.

<img src="./images/fig20.jpg"  width="400"/>   
