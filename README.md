# AI ML Task README

This repository contains code for performing object detection using YOLOv8 model. The code is written in Python and designed to be run in Google Colab environment.

## Overview

This project utilizes YOLOv8, a state-of-the-art object detection model, for detecting objects in images. The code provides functionalities for training the model on a custom dataset, validating the trained model, and making predictions on new images.

## Dependencies

Make sure you have the following dependencies installed:

- [Ultralytics](https://github.com/ultralytics/yolov5): A Python package for deep learning object detection. You can install it via pip: pip install ultralytics

## Usage

- Training
Mount Google Drive: The code expects the dataset to be stored in Google Drive
Navigate to the directory where your dataset is stored
Train the YOLOv8 model using the provided dataset

- Validation
After training, you can validate the trained model on a validation dataset just select the mode = val

- Prediction
Start making the  predictions on new images using the trained model selectin the model and providing the image

- Viewing Predictions
The predictions made by the model on test images will be stored in the directory: /content/drive/MyDrive/Class/Yolo_V8/runs/detect/predict.

## NOTE
To predict the material object in a custom image, upload the image to Colab and run the prediction code with the appropriate image source.

## Additional Notes
- This code is designed to be run in Google Colab environment.
- Ensure that your dataset is structured according to the requirements specified in data.yaml.
- Adjust parameters such as epochs, imgsz, and conf as needed for your specific use case.
- For further information on YOLOv8 and its parameters, refer to the Ultralytics documentation.
