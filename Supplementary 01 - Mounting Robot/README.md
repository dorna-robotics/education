# **Mounting Robot**

## **Overview**
This guide provides step-by-step instructions for securely mounting the Dorna TA robotic arm.

## **Parts**
| **Part** | **Description/Image** |
|---|---|
| [1 x Dorna base plate](https://dorna.ai/) | <img src="./Assets/Images/1.png" alt="Dorna Base Plate" width="100"/> |
| [1 x Dorna TA robotic arm](https://dorna.ai/) | <img src="./Assets/Images/2.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [4 x M5 6mm screws](https://www.mcmaster.com/90128A228/) | <img src="./Assets/Images/3.png" alt="Screw" width="100"/>  |
| [1 x Ethernet Splitter](https://a.co/d/cWE83wG) | <img src="./Assets/Images/4.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [2 x Short Ethernet Cables](https://a.co/d/0XHGOBJ) | <img src="./Assets/Images/5.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [1 x Long Ethernet Cable](https://a.co/d/5KD8N7V) | <img src="./Assets/Images/6.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [1 x USB C Cable](https://a.co/d/gTFuSt4) | <img src="./Assets/Images/7.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [1 x Rapberry Pi Power Supply](https://a.co/d/gO7Qurn) | <img src="./Assets/Images/8.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [1 x Solenoid Power Supply](https://a.co/d/4ajOn8z) | <img src="./Assets/Images/9.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [1 x Solenoid Valve](https://a.co/d/a9mEhc8) | <img src="./Assets/Images/10.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [1 x Solenoid I/O Wires](https://a.co/d/6ludXXV) | <img src="./Assets/Images/11.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [1 x Power Cable](https://a.co/d/902MPWC) | <img src="./Assets/Images/12.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [1 x DB25 Cable](https://a.co/d/5uJYNzg) | <img src="./Assets/Images/13.png" alt="Dorna TA Robotic Arm" width="100"/> |
| [1 x DB9 Cable](https://a.co/d/fVw5Gf7) | <img src="./Assets/Images/14.png" alt="Dorna TA Robotic Arm" width="100"/> |

## **Assembly instructions**

1. **Secure the base plate**  
   Attach the base plate to your surface.  
   <br/>

2. **Mount the robotic arm**  
   Using the 4 M5 6mm screws, secure the robotic arm to the base plate through the holes located at positions ``B1``, ``B3``, ``D1``, and ``D3`` on the base plate.  
   <img src="./Assets/Images/15.jpg" alt="Mounting Holes" width="400"/>  
   <br/>  
   <img src="./Assets/Images/16.jpg" alt="Robotic Arm Mounted" width="400"/>

### **Wiring Instructions**

1. **Connect the Camera**  
   Using a USB 3.0 extension cable, connect the wire coming off the camera on the robot to one of the blue USB 3.0 ports on the Raspberry Pi.
   <br/>
   <img src="./Assets/Images/17.jpeg" alt="Mounting Holes" width="400"/>  
   <br/>

3. **Connect to the Internet**  
   Start by connecting two short Ethernet cables to the Ethernet splitter on the control box.
   <br/>
   <img src="./Assets/Images/18.jpg" alt="Ethernet Splitter" width="400"/>  
   <br/>  
   Next, connect one of the Ethernet cables to the Raspberry Pi. Also, connect a short USB-C cable to one of the black USB 2.0 ports on the Raspberry Pi.  
   <br/>
   <img src="./Assets/Images/19.jpg" alt="Raspberry Pi Connection" width="400"/>  
   <br/>  
   Then, plug the USB-C cable you just connected to the Raspberry Pi into the back of the Ethernet splitter. While back here, connect a long Ethernet cable to the port on the back of the splitter. This cable should run to your router or any Ethernet port with internet access.
   <br/>
   <img src="./Assets/Images/20.jpg" alt="Ethernet Connection" width="400"/>  
   <br/>  
   Finally, connect the other Ethernet cable at the front of the splitter to the Dorna TA control box.
   <br/>
   <img src="./Assets/Images/21.jpg" alt="Dorna TA Control Box" width="400"/>  
   <br/>

5. **Powering the Solenoid Valve**  
   Use the solenoid power supply and the female barrel connector attached to the solenoid to power the solenoid valve. Also, connect the red and black solenoid wires to the solenoid: the red wire should go to the "+" terminal, and the black wire should go to the "-" terminal on the ports labeled "control."
   <br/>
   <img src="./Assets/Images/22.jpg" alt="Solenoid Valve" width="400"/>  
   <br/>  
   Connect the black wire to the 0 output pin and the red wire to the 24V port on the front of the control box (to the left of the black wire).
   <br/>
   <img src="./Assets/Images/23.jpg" alt="Control Box" width="400"/>  
   <br/>
   Using the P port on the solenoid and run a tube from that port to your air compressor.
   <br/>
   <img src="./Assets/Images/24.jpg" alt="Control Box" width="400"/>  
   <br/>

7. **Powering the Raspberry Pi**  
   Use the provided USB-C power supply to connect to the USB-C port on the side of the Raspberry Pi to power it.
   <br/>
   <img src="./Assets/Images/25.jpg" alt="Control Box" width="400"/>  
   <br/>

8. **Connecting Robot**
   Connect the DB25 and DB9 wires to the back of the robot. Keep in mind that this will lock the motors, so ensure the robot is in a safe position.
   <br/>
   <img src="" alt="Control Box" width="400"/>  
   <br/>
   Run these wires down to the back of the control box and connect them to their corresponding ports. 
   <br/>
   <img src="./Assets/Images/26.jpg" alt="Control Box" width="400"/>  
   <br/>
   Finally, connect a power cable to the back of your control box and outlet. 
   <br/>
   <img src="" alt="Control Box" width="400"/>  
   <br/>
