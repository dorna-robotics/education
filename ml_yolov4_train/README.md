## **Yolov4 Training**

Before running this colab, make sure to set the runtime to GPU for faster training (**Runtime** > **Change runtime type** > **Hardware accelerator**)

### **Creating Dataset**
1. **Define Object Catagories**
  - Determine the objects and or defects you want to detect (e.g., cats, dogs, cars, good apple, bad apple).
  - In our sample we will define our object categories as **good cardamom** and **bad cardamom**.
2. **Collect Images**
  - Take photos using your choice of camera (e.g., Google Images, mobile phone, personal camera). Ensure diversity in angles, lighting, and backgrounds (include conditions you expect to see later during the detection process).
  -This is sample image set, you may chose to vary conditions and set size depending on the accuracy you hope to achieve: [sample images](https://photos.app.goo.gl/FtLV9HDPrkQnURrq7)
3. **Labeling the Images** (Here we use a free online labeling tool called [**roboflow**](https://roboflow.com/) to label and create the dataset.)
  - Login or create an account at https://roboflow.com/
  - Next create a project using the **New Project** button in the top right corner of your screen.
  #### ![Dorna Workmark](https://i.imgur.com/94aYGQf.png)
  - Select the right project type for your application (e.g., object detection, instance segmentationm, keypoint detection)
  - From the **Upload Data** tab on the left upload all your images.
  #### ![Dorna Workmark](https://i.imgur.com/qyF42FP.png)
  - From Annotation tab use the **Polygon Tool** and or **Smart Polygon Tool** to label the desired objects in each image.
  -Once you have finished the labeling and you are ready to generate the dataset. Click on the **Generate** tab.
  #### ![Dorna Workmark](https://i.imgur.com/HjDKyh1.png)
  - In the **Generate** tab, create a new version using the button in the top left corner.
  - Under **Preprocessing** section, make sure to select the following, before creating the dataset:
    - **Auto-Orient**
    - **Resize and stretch to 416x416**
  #### ![Dorna Workmark](https://i.imgur.com/bbZh7xv.png)
  - Under the **Versions** tab, select the right dataset version, and click **Export Dataset**.
  #### ![Dorna Workmark](https://i.imgur.com/xo2zuSF.png)
  - Select **YOLO Darknet**, check the box next to **show download code** then click Continue.
4. **Running the Colab**
  - At the top of the first cell replace the pre-placed roboflow download code with your own. It should look something like this.
  ```
!pip install roboflow
import cv2
from roboflow import Roboflow
rf = Roboflow(api_key="hidden")
project = rf.workspace("dorna").project("cardamom-good-bad")
version = project.version(23)
dataset = version.download("darknet")
```
  - In the same box where it says percentage_test = 10 you can change the percentage of images you want as a test images.
  - At the bottom of the box you will notice an Augmentation Dictonary, there you can find comments explaing the diffrent ways you can augment your images to make your detections better.
  - Finally, it is a simple as running all of the cells top to bottom.
