## **YOLOv4 Training**

Before starting, ensure your Colab environment is set to use GPU for faster training. Go to **Runtime** > **Change runtime type** > **Hardware accelerator** and select **GPU**.

### **Creating Your Dataset**

1. **Define Object Categories**
   - Identify the objects or defects you want to detect (e.g., cats, dogs, cars, good apple, bad apple). In this example, we use categories **1, 2, 3, 4,** and **5**.

2. **Collect Images**
   - Capture photos using your camera (e.g., Google Images, mobile phone, or personal camera). Ensure diversity in angles, lighting, and backgrounds. The sample image set can be viewed [here](https://photos.app.goo.gl/FtLV9HDPrkQnURrq7). Adjust conditions and set sizes based on the accuracy you aim to achieve.

3. **Label the Images**
   - Use a labeling tool like [**Roboflow**](https://roboflow.com/) to label and create your dataset.
     - Sign in or create an account at [Roboflow](https://roboflow.com/).
     - Create a new project by clicking **New Project**.
       ![New Project](https://i.imgur.com/94aYGQf.png)
     - Select the project type suitable for your application (e.g., object detection).
     - Upload your images via the **Upload Data** tab.
       ![Upload Data](https://i.imgur.com/qyF42FP.png)
     - Use the **Polygon Tool** or **Smart Polygon Tool** under the **Annotation** tab to label objects in each image.
     - After labeling, navigate to the **Generate** tab to create the dataset.
       ![Generate Dataset](https://i.imgur.com/HjDKyh1.png)
     - In the **Generate** tab:
       - Create a new version using the button in the top left corner.
       - Under **Preprocessing**, select:
         - **Auto-Orient**
         - **Resize and stretch to 416x416**
           ![Preprocessing](https://i.imgur.com/bbZh7xv.png)
     - Go to the **Versions** tab, select the desired dataset version, and click **Export Dataset**.
       ![Export Dataset](https://i.imgur.com/xo2zuSF.png)
     - Choose **YOLO Darknet**, check **Show download code**, then click **Continue**.

4. **Running the Colab Notebook**
   - Replace the placeholder Roboflow download code in the first cell with your own code, which should look like this:
     ```python
     !pip install roboflow
     import cv2
     from roboflow import Roboflow
     rf = Roboflow(api_key="your_api_key_here")
     project = rf.workspace("your_workspace_name").project("your_project_name")
     version = project.version(version_number)
     dataset = version.download("darknet")
     ```
   - Modify the percentage of images used for testing by changing the value in `percentage_test = 10`.
   - Run all cells in the notebook from top to bottom to complete the setup and start the training process.