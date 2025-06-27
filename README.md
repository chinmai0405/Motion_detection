##Motion Recognition with IMU Sensor Fusion
This project implements a real-time gesture detection system using a Raspberry Pi paired with the Sense HAT. By combining readings from the accelerometer and gyroscope, the system can classify four distinct types of motion and display visual feedback on the onboard LED matrix.

Overview
The classifier distinguishes between these gesture categories:

move_none

move_circle

move_shake

move_twist

A neural network is trained to process 1-second windows of motion data (50 samples per second, each sample containing 6 values from accelerometer and gyroscope). The trained model is exported as a TensorFlow Lite file for efficient deployment on the Raspberry Pi.

Project Components
capture.py: Collects labeled IMU data sequences for training.

predict.py: Loads the TensorFlow Lite model on the Pi, classifies motion in real time, and controls the LED matrix display.

motion_model.tflite: The trained model ready for inference.

Lab05_Gesture_Train.ipynb: Notebook for training the neural network and converting it to TFLite format.

motion_data/: Directory containing saved IMU recordings, organized by gesture label.

images/: Folder with photos showing LED output during predictions.

requirements.txt: Lists all necessary Python dependencies.

.gitignore: Configuration for excluding specific files from version control.

Setup Guide
Install the Python libraries specified in requirements.txt.

Use capture.py to record motion data samples on the Raspberry Pi.

Train the model by running Lab05_Gesture_Train.ipynb locally or in Google Colab.

Convert the trained model to TensorFlow Lite format (.tflite).

Launch predict.py to begin real-time classification and LED visualization.

Hardware Requirements
Raspberry Pi equipped with Sense HAT

Integrated IMU sensors (accelerometer and gyroscope)

RGB LED matrix display for visual feedback

Motion-to-Color Mapping
Motion Type	LED Color
move_none	Off (Black)
move_circle	Red
move_shake	Green
move_twist	Blue

