# **7. Vision Basics**

Computer vision is pivotal in programming industrial robotic systems due to its ability to provide robots with the "eyes" needed to interpret and interact with their environment. This technology enables robots to perform tasks with high precision and adaptability, such as quality inspection, object sorting, and assembly operations. By leveraging computer vision, robots can identify and locate objects, assess their orientation, and make real-time decisions, which significantly enhances their efficiency and accuracy in manufacturing processes.

Traditional robotic systems often rely on pre-defined paths and operations, limiting their adaptability to changes in the production line. In contrast, robots equipped with computer vision can dynamically adjust their actions based on visual feedback, allowing them to handle a variety of tasks and adapt to new or unexpected situations. This capability is crucial for modern manufacturing environments that demand high levels of customization and rapid production changes. By integrating computer vision, industrial robots become more versatile, capable, and essential for the future of automated manufacturing.
In this section, we will review the fundamental concepts of computer vision that will help us for adding basic vision and detection features to our robot programming toolbox. This chapter will benefit from the well-known detection library OpenCV for its goal. The Dorna robotics also features simple tools, that let you use the OpenCV features more easily for your robotic application.



## **Fundamental Concepts of Vision in Robotics**

The ultimate goal of using vision systems in robotics is to convert the information stored in captured images of the robot’s surroundings into three-dimensional data about objects. This transformation enables us to plan the robot's movements and interactions with these objects. In many real-world scenarios, the state of the environment is not entirely deterministic, so we need to continually update our information about the surroundings. Utilizing cameras and vision systems is the most versatile and effective way to achieve this dynamic understanding.

Basic vision methods, such as those implemented in the OpenCV library, rely on detecting patterns in images and subsequently extracting spatial data from these patterns. Various detection techniques hinge on identifying specific patterns within the image. For instance, edge detection, feature matching, and contour finding are fundamental processes that allow a vision system to interpret the spatial configuration and characteristics of objects within its field of view. By recognizing these patterns, the system can infer distances, shapes, and orientations, which are crucial for accurate object manipulation and navigation.

### *Types of Cameras*
When it comes to vision in robotics, a variety of cameras can be employed, each offering unique advantages depending on the application. The types of cameras can be categorized based on the type of the data they offer, or based on the method they acquire their data. 

#### *RGB Cameras*
RGB cameras capture images in the red, green, and blue color channels, producing high-resolution, color images. They are widely used for tasks such as object recognition, color-based sorting, and environmental mapping. However, they do not provide direct information about the distance or depth of objects.

#### *Depth Cameras*
Depth cameras, such as Microsoft Kinect and Intel RealSense, provide information about the distance of objects from the camera. This additional dimension of data is crucial for a variety of robotic applications. Knowing the exact distance and dimensions of an object allows for precise grasping and manipulation. Depth data enables the creation of accurate 3D maps of the environment.

A depth map means per-pixel depth values, this value measures how far a ray originating from that pixel can go before intersecting with an opaque surface. 

|![](./images/fig1.jpg) | 
|:--:| 
| *The depth value of a pixel* |

 Different technologies are used for extracting the depth data. For example:

 - **Stereo Cameras**: Stereo cameras use two or more lenses to mimic human binocular vision, allowing the system to perceive depth through the parallax effect. By comparing the images from the different lenses, stereo cameras can calculate the distance to objects. This method is particularly useful for creating real-time maps of unknown environments.

 - **LiDAR**: LiDAR (Light Detection and Ranging) systems emit laser beams and measure the time it takes for the beams to return after hitting an object. This technology creates highly accurate 3D models of the environment and is commonly used in autonomous vehicles and drones.

|![](./images/fig2.jpg) | 
|:--:| 
| *Showing an RGB+depth map, The blue means near, and red means far from the camera* |


The camera installed on the Dorna TA that is used in this course is an Intel Realsense D450 that outputs a depth map as well as the RGB map of the surroundings. It means that for each of the 1280x720 pixels, we get 3 color values (red, green, and blue) plus a depth value. This camera calculates depth using the two-channeled stereoscopic technology and its depth value has around 2% accuracy at a distance of 50cm (the error will increase for larger distances and decreases if the object is closer) meaning that it may report the distance of a real 50cm distance as 51 or 49 cm.

There are many options for camera installations in the field of robotics. In some cases, the camera is installed somewhere fixed with respect to the robot’s base and covers the robot’s working range in its field of view. But in the case of the Dorna TA robot, the camera is attached to the robot’s arm. This configuration is called the “Eye in Hand” configuration. This allows the robot to have a dynamic viewpoint, providing real-time visual feedback from the perspective of the tool or gripper. This configuration enhances the robot's ability to interact with objects, offering precise control in tasks like assembly, inspection, and manipulation.  This configuration has enhanced flexibility and versatility but demands complex calibration and coordination, and sometimes the camera can be blocked by the arm or other objects, limiting visibility.

|![](./images/fig3.jpg) | 
|:--:| 
| *Intel Realsense D450 camera and its depth of field* |

<div style="border: 1px solid black; padding: 10px; background-color: #faeeb6;">
<h3 style="margin-top: 0;">Note</h3>

The camera coordinate frame is attached to the camera and contains enough information to represent the camera’s position and orientation in the 3D world. The origin of this frame resides somewhere on the light sensors of the camera where the image is being projected, its Z axis is perpendicular to the projection screen, and the X, and Y axes, are usually parallel to the projection screen. If you view these axes from the camera’s perspective, you’ll see that the X-axis points toward your right, and the Y-axis points downward. You can observe these axes in the figure above.

We can also talk about another coordinate frame, the image CF which is a 2 dimensional coordinate frame that we use to identify points in the images. This CF works like this: the origin of the coordinate frame resides in the upper-left corner of the image. The X axis is toward the right, and the Y axis is toward down. The input image has a width and height parameter measured in the unit of pixels, which is constant and depends on the type of camera you are using. For example **height** = 720px and **width** = 1280px for the camera we are going to use. 

The point in the lower right corner of the image is the point with maximum values of x and y equal to width and height respectively. Any point outside the rectangle defined by the screen height and width is considered out of bounds and is inaccessible using our maps.

|![](./images/fig4.png) | 
|:--:| 
| *Image coordinate frame* |

</div>

---
## **Detection GUI**

To find the position of the objects in the environment, the application should first automatically detect the presence, the number, and the position of the desired objects relative to the camera frame, based on the input image. The detection part is done mostly based on the input RGB map, but to extract the 3d position information, we usually have to use the depth map. 

OpenCV performs object detection through a combination of image processing techniques. The process generally involves several key steps. Here we will not go through a detailed review of how OpenCV works, and how an OpenCV workflow should be created because that would take a complete course for itself. Instead, we will learn how to use OpenCV through a prepared graphical user interface to create simple yet useful programs for a wide range of robotic applications. 

Now let’s start working with this GUI by first opening the Jupyter environment using Dorna Lab. Then download and navigate the notebook “detection_gui” from the “example” folder of the [“dorna_vision” repository on GitHub](https://github.com/dorna-robotics/dorna_vision). Run the code cell in that notebook so the GUI starts working.

Here is the first look at the GUI you’ll encounter with:

|![](./images/fig5.jpg) | 
|:--:| 
| *Detection GUI* |

### *Input and Adjustments*
You should first select your input source, in our case, it would be the input from the Intel RealSense camera, but you are also able to use a captured image as your input by choosing the option from the “Source” dropdown list. Click on the “Capture” button, so the captured image (shown below the GUI) gets updated.

Note that it’s important to click on the **“Terminate the app”** button when you were finished working with the GUI.

Next step is to perform adjustment on the raw input image before start working on detection. These adjustments are going to help the program to perform better detections. So start by clicking on the “Visual adjustment” tab. The options for adjusting the image are as below:

#### *Region of Interest*
Consider this scenario: you are programming a vision system for a conveyor belt in a factory that moves small boxes around. Your goal is to check the boxes passing on the conveyor. However, the camera's field of view includes a lot of unnecessary scenery from the environment. There are parts of the input image that you can confidently delete without causing any errors in the vision process. These are regions where you know the boxes won’t pass.

In this scenario, masking out these regions is beneficial. First, you reduce the number of pixels your processing unit has to handle for detection. Secondly, by specifying a valid region, you lower the possible risks of erroneous detections from invalid regions.

To specify the region of interest for your application, head to the “Region of Interest” sub-panel, and start drawing the desired polygon on the image below by clicking on it. 

|![](./images/fig6.jpg) | 
|:--:| 
| *Region of  interest specified using the blue polygon, notice that hovering the mouse on the input image will show you options for interacting with it. The most important ones let you zoom and move the picture around* |

Check the “Apply the ROI” checkbox to make the region of interest active (this option is also present in the other adjustment sub-panel sections and should be checked if we want to use that adjustment feature). You can also invert this region (the region of interest would then be outside the polygon instead of inside it) by checking the “Inver the region” checkbox.

#### *Intensity*
