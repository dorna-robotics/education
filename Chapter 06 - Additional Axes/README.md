# **6. Additional Axes**

The additional axes refer to the supplementary degrees of freedom added to a robot's primary configuration to enhance its range of motion, flexibility, and versatility. These auxiliary axes, which are also known as external or extra axes, can be integrated into a robotic system to enable more complex and precise operations, beyond the capabilities of the standard six-axis robots commonly used in industrial applications.

The primary purpose of auxiliary axes is to extend the robot's reach and allow for more intricate movements. For instance, a robot with a seventh axis can move along a linear track, expanding its operational workspace significantly. This additional axis is particularly useful in tasks such as welding, painting, or material handling, where the robot needs to access various points within a larger area. Similarly, an eighth or ninth axis might be added to enable rotational movements or to manipulate additional tooling, providing the robot with the ability to perform multi-step processes without the need for repositioning.
As for the Dorna TA robot, In addition to the six axes of the robot, the controller can operate two additional axes. For each of these two axes, the control system has an additional motor control output and an encoder input port.

In this section, we will go over setting up and using the auxiliary axes with the robot.
In the context of auxiliary axes, we have a motor (optional) that runs an axis (joint) through a gearing mechanism. The controller uses an encoder (optional) data to report the value of that axis as j6, or j7 (depending on the axis number). These two new degrees of freedom in addition to the actuator’s 6 joint values will give us a system with a total of 8 axes of control. 

The control system can handle two new components for each of the additional axes, these two components are explained below. For each additional axis at least one of them should be present.