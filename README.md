README
#This repository contains code for performing object detection using YOLOv8 model. The code is written in Python and designed to be run in Google Colab environment.

#Overview
This project utilizes YOLOv8, a state-of-the-art object detection model, for detecting objects in images. The code provides functionalities for training the model on a custom dataset, validating the trained model, and making predictions on new images.

#Dependencies
Make sure you have the following dependencies installed:
Ultralytics: A Python package for deep learning object detection. You can install it via pip:
pip install ultralytics


#Training
Mount Google Drive: The code expects the dataset to be stored in Google Drive. Run the following code to mount your Google Drive:
from google.colab import drive
drive.mount('/content/drive')

#Navigate to the directory where your dataset is stored:
%cd /content/drive/MyDrive/Class/Yolo_V8

#Train the YOLOv8 model using the provided dataset:
!yolo task=detect mode=train model=yolov8s.pt data=data.yaml epochs=25 imgsz=224 plots=True

#Validation
After training, you can validate the trained model on a validation dataset:
!yolo task=detect mode=val model=runs/detect/train/weights/best.pt data=data.yaml

#Prediction
To make predictions on new images using the trained model:
!yolo task=detect mode=predict model=runs/detect/train/weights/best.pt conf=0.25 source=data/test/images

#Viewing Predictions
The predictions made by the model on test images will be stored in the directory: /content/drive/MyDrive/Class/Yolo_V8/runs/detect/predict. You can display these predictions using the following code:
import os
from IPython.display import display, Image
folder_path = "/content/drive/MyDrive/Class/Yolo_V8/runs/detect/predict"
image_files = [f for f in os.listdir(folder_path) if os.path.isfile(os.path.join(folder_path, f))]
for image_file in image_files:
    image_path = os.path.join(folder_path, image_file)
    display(Image(filename=image_path))

#Note
To predict the material object in a custom image, upload the image to Colab and run the prediction code with the appropriate image source.

#Additional Notes
This code is designed to be run in Google Colab environment.
Ensure that your dataset is structured according to the requirements specified in data.yaml.
Adjust parameters such as epochs, imgsz, and conf as needed for your specific use case.
For further information on YOLOv8 and its parameters, refer to the Ultralytics documentation.
