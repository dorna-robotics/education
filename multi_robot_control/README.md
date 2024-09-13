# **Tic-Tac-Toe Automation**

## **Overview**
This project involves using two Dorna TA robots that communicate with each other to play a game of Tic-Tac-Toe. This introduces students to the exciting world of multi-robot automating by creating a game of Tic-Tac-Toe using two Dorna TA robotic arms. Participants will learn how to assemble the robots, configure their communication through I/O pins, and program their movements to autonomously play the game. By integrating robotics, programming, and real-time communication, students will understand how machines can work collaboratively to complete tasks in a structured environment.

Throughout the project, students will write Python scripts to control the robots, handle game logic, and communicate through I/O ports to signal moves and update the game board. The robots will pick and place Tic-Tac-Toe pieces based on board positions, communicating their actions to ensure that both robots know when and where to place pieces. The course emphasizes hands-on learning, enabling students to interact with robots, troubleshoot code, and gain valuable experience in automation.

### **Main Learning Objective: Communication Between Robots**
The primary learning objective of this project is to develop a reliable communication system between two robots to automate a game of Tic-Tac-Toe. Communication is achieved through the I/O ports on the robots, which transmit signals to indicate game board positions and actions.


**How We Achieve Communication**
<br/>
In this project the robots need to communicate with eachother to know what spaces are avalible and when it is safe for it to make a move. The robots communicate by sending signals through their I/O ports. These signals represent different positions on the game board and instruct the robots on where to place the game pieces.

The I/O ports 1-4 send binary values, which the robots interpret as coordinates on the Tic-Tac-Toe grid. By utilizing a predefined mapping between I/O pin values and board positions, the robots can accurately read the table and make a move based on the game logic. It also uses the pin signal from pin 5 to know when it is safe to make a move. This is done by Robot A setting output pin 5 to equal 1 when it is making a move that action sets input pin 5 on Robot B equal to 1 indicating to Robot B that Robot A is working and it must wait to make a move.

Here’s the table that defines the communication protocol between the robots:<br>
*Note that the I/O signals are formated [pin 1, pin 2, pin 3, pin 4]*

| (0, 0) - Top-left<br>[0, 0, 0, 1] | (0, 1) - Top-center<br>[0, 0, 1, 0] | (0, 2) - Top-right<br>[0, 0, 1, 1] |
|:-------------------------------------:|:-------------------------------------:|:-------------------------------------:|
| **(1, 0) - Middle-left<br>[0, 1, 0, 0]** | **(1, 1) - Center<br>[0, 1, 0, 1]** | **(1, 2) - Middle-right<br>[0, 1, 1, 0]** |
| **(2, 0) - Bottom-left<br>[0, 1, 1, 1]** | **(2, 1) - Bottom-center<br>[1, 0, 0, 0]** | **(2, 2) - Bottom-right<br>[1, 0, 0, 1]** |


## **Parts**
| **Part** | **Description/Image** |
|:---|---|
| [Robot mounting parts](https://github.com/dorna-robotics/education/tree/main/mount_robot#parts) |   |
| [Robot suction gripper parts](https://github.com/dorna-robotics/education/blob/main/attach_suction_gripper/README.md#parts) |   |
| 3 x Base plate connectors | <img src="https://i.imgur.com/ApHx3pN.png" alt="Base Plate Connectors" width="100"/> |
| 10 x Tic-tac-toe game pieces | <img src="https://i.imgur.com/eWH0BdG.png" alt="Set of Chips" width="120"/> |
| 1 x Tic-tac-toe game board | <img src="https://i.imgur.com/ZgE4bXc.png" alt="Game Board" width="100"/> |
| 2 x Tic-tac-toe game piece holders | <img src="https://i.imgur.com/Zz2rPqp.png" alt="Game Piece Holders" width="100"/> |

## **Assembly instructions**

1. **Mount the robots**  
   Follow the [mounting instructions](https://github.com/dorna-robotics/education/tree/main/mount_robot#assembly) to mount both robots.

2. **Attach the suction grippers**  
   Attach the suction grippers to both robots following the [suction gripper instructions](https://github.com/dorna-robotics/education/blob/main/attach_suction_gripper/README.md#assembly).

3. **Connect the base plates**  
   Use the three base plate connectors to join the two base plates on the short edge furthest from the robots. 

   <img src="Dorna_Image" alt="Base Plate Connectors" width="400"/>

5. **Install the tic-tac-toe game board**  
   Secure the game board to the base plates using the hole located at ``C9`` on both plates.  
   <img src="Dorna_Image" alt="Game Board" width="400"/>

6. **Attach the game piece holders**  
   Mount the game piece holders using the holes at ``B3`` and ``D3``.  
   <img src="Dorna_Image" alt="Game Piece Holders" width="400"/>

7. **Your assembly is complete!**  
   <img src="" alt="Finished" width="400"/>
