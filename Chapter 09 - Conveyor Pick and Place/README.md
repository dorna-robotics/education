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
|3 x toy cubes|<img src="./images/fig22.jpg" alt="cubes" width="200"/> | 

## **Assembly instructions**


1. **Wiring Conveyor Belt**
    Start by detaching the motor from the conveyor belt, this can be done by removing the 4 bolts on the front of the belt’s chassis.

<div align="center">
<img src="./images/fig8.jpg"  width="400"/>   
</div>

Solder an 18-gauge wire to both the power and ground terminals on the motor. Solder the red and black to the same terminals shown below.

<div align="center">
<img src="./images/fig9.jpg"  width="400"/>   
</div>
   
Reattach the motor. Then, using the green terminals on the front of Dorna's control box, connect the Red to the 24v and the black to one of the output connections (in this case, 1 was used). Here we can also observe how the proximity sensor has also been attached to the controller as an input device (here it is input 6)

<div align="center">
<img src="./images/fig10.jpg"  width="400"/>   
</div>

Please follow the indication below for the connections of wire of the input and output systems in this project:

<div align="center">
<img src="./images/wire-colors.jpg" />   
</div>

Now the belt is connected and it can be controlled via the output system of the robot. 

2. **Mounting Conveyor Belt**
   First, use the four black M5 bolts to attach the conveyor mounting brackets to the Aluminum Mounting Plate.

<div align="center">
<img src="./images/fig11.jpg"  width="400"/>   
</div>

Then, use the four black M3 bolts and the M3 nuts to mount the conveyor belt to its brackets.

<div align="center">
<img src="./images/fig12.jpg"  width="600"/>   
</div>

3. **Mounting Sensor**
Mount the Infrared Sensor to the left conveyor mounting bracket through the hole on the bracket and plastic nuts on the sensor. Pay special attention to aligning the sensor at the edge of the conveyor belt to get the most accurate readings.

<div align="center">
<img src="./images/fig13.jpg"  width="400"/>   
</div>

4. **Mount the robots**   
   Follow the [mounting instructions](https://github.com/dorna-robotics/education/tree/main/mount_robot#assembly) instructions to prepare the robot. Start by pressing the four M8 nuts into the hexagonal holes on the bottom of the Dorna to Mounting Plate Adapter to mount the robot on the plates.

<div align="center">
<img src="./images/fig14.jpg"  width="400"/> 
</div>
<div align="center">
<img src="./images/fig15.jpg"  width="400"/>   
</div>

   Using the four black M8 bolts attach the Dorna 2 to the Mounting Plate Adapter. Using the four silver M5 bolts attach the mounting plate adapter to the aluminum mounting plate. 

<div align="center">
<img src="./images/fig16.jpg"  width="400"/>   
</div>

5. **Attach the pneumatic gripper**  
   Attach the pneumatic grippers to the robot following the #proper link. Install the Jaws on the gripper.

<div align="center">
<img src="./images/fig17.jpg"  width="400"/>   
</div>

Attach the tubing to the solenoid valve. 

<div align="center">
<img src="./images/fig18.jpg"  width="400"/>   
</div>

Run one tube from the solenoid valve to the compressor.

<div align="center">
<img src="./images/fig19.jpg"  width="400"/>   
</div>

We should also connect the solenoid wires to the controller as another output device (here we have used output 7) like below.

<div align="center">
<img src="./images/fig20.jpg"  width="400"/>   
</div>



## **I/O System Setup**

After setting up the proper wiring for the input (proximity sensor) and output (conveyor + pneumatic gripper) systems, we should set them up and test them on the software side.

- Test the proximity sensor, by checking its input value in Dorna Lab’s I/O panel. Specify approximately, how far away the sensor can detect objects from.

- Test the conveyor belt, by controlling its output value using Dorna Lab’s I/O panel. Use a stopwatch to calculate the belt’s moving time, and a ruler to find its travel length, and calculate its speed using these measured lengths and time.

- Test the pneumatic gripper by turning on/off the corresponding output using Dorna Lab's I/O panel, check if it's possible to hold to the cubes 

<div align="center">
<img src="./images/fig21.jpg"  width="300"/>   
</div>

## **Code**

The goals for coding in this project are 

- We want the program to synch the conveyor's movement with the proximity sensor's input. When the sensor's input becomes active (a box is in front of it) the conveyor should stop moving, and the robot should perform pick and place, and after its completion, the conveyor should move again.

- When the sensor's input has suddenly activated (the box has arrived) the robot should perform a pick and place operation to pick the box and put it in the front of the conveyor. The picking position and placing position should be carefully specified by hand-training the robot: Place a box on the turned-off conveyor's front, choose this initial position of the box as the "placing" position, and use hand-training to carefully find the placing position ```xyz``` values. Now turn on the conveyor until the sensor detects the box and stops the conveyor, that would be the box's "picking" position. Use hand training again to find the picking position's ```xyz``` values. Use the picking and placing position in your code for the pick-and-place operation.

- It would be also wise to specify a middle point for the pick-and-place motion, based on what you've learned about this kind of motion, choose the middle point's ```xyz``` position using hand-training.

The code for this project is available [here](./codes/conveyor.ipynb).