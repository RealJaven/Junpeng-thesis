
---

# Structure Overview

## Directory Structure

### `second_stage_datasets/`

This folder contains all datasets utilised for training classifier models. It is organised as follows:

- **`cropped/`**: In a format suitable for classifier training, including cropped images of individual cells and 
  corresponding labels.

### `yolo_datasets/`

A folder for all datasets used in training the YOLO model. It is structured as follows:

- **`images/` and `labels/`**: Formatted according to YOLOv5 specifications, containing images and corresponding label 
  files for object detection training.

### `segment-anything/`

This directory contains the code for the 'Segment Anything' model, which is used to segment cells from images.

### `yolov5/`

This directory contains the associated training tools and resources for the YOLOv5 model.

- **`detectorGUI.py`**: A graphical user interface for the detector, allowing for easy and intuitive use of the 
model for object detection tasks. If you are looking to change the appearance of the GUI, you can do so by modifying 
this file.

### `classifier_train/`

A toolkit for training classifiers, providing scripts essential for training and evaluating 
classification models.

---

## GUI Features and Usage

Download the GUI from the following link:
https://drive.google.com/file/d/1CMFyE-5hfnULCL_FHFY3jdBxEV4IyF6S/view?usp=drive_link

### Loading and Running Detection

- **Load Folder**: Click this button to open a dialog where you can select a folder containing the images.
- **Run**: After loading your images, click here to start the object detection process. The progress will be shown in 
the green progress bar at the top.

![alt text](https://github.com/RealJaven/Junpeng-thesis-2023S1/blob/main/readme_img/1.PNG?raw=true)
![alt text](https://github.com/RealJaven/Junpeng-thesis-2023S1/blob/main/readme_img/2.PNG?raw=true)

### Navigation and Statistics

- The GUI provides navigation buttons ('Previous' and 'Next') to move between images.
- It also displays 'Local Statistics' for the current image and 'Global Statistics' for all images in the loaded folder, 
which include counts of each object class.


### Interaction with Detected Objects

- Once the detection is complete, the GUI will display the images along with the bounding boxes around detected objects.
- Detected objects are highlighted in different colors indicating their classifications.
- Clicking on a bounding box will display the current classification for that object in the 
'Current bounding box information' pane.



### Editing Object Classifications

- If the object classification needs to be corrected, you can change the predicted label by clicking on the bounding box 
and then clicking on the 'Change Label' button.
- A dialog box will appear where you can choose the correct label from a dropdown menu.
- After selecting the new label, click 'OK' to confirm the change or 'Cancel' to keep the previous label.

![alt text](https://github.com/RealJaven/Junpeng-thesis-2023S1/blob/main/readme_img/4.PNG?raw=true)
![alt text](https://github.com/RealJaven/Junpeng-thesis-2023S1/blob/main/readme_img/5.PNG?raw=true)


## Label Management and Output

Upon completion of the detection and potential modification process, 
the program will output two folders within the selected folder:

- **`labels/`**: This folder contains the original predicted labels in YOLOv5 format. 
Each image in your dataset will have a corresponding label file detailing the bounding boxes and class predictions.

- **`modified-labels/`**: This directory is dynamically updated to reflect any changes made by the user through the GUI.
When a user modifies a label via the GUI, the corresponding label file in this folder is updated to reflect the change.

![alt text](https://github.com/RealJaven/Junpeng-thesis-2023S1/blob/main/readme_img/6.PNG?raw=true)


### Understanding the Label Files

- Each label file is a simple text file that contains one or more lines, each representing a detected object.
- The format of each line is `[class] [x_center] [y_center] [width] [height]`, 
where coordinates and dimensions are normalized to the size of the image.
---
