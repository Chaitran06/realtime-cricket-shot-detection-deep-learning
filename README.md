# Real-Time Cricket Shot and Umpire Gesture Detection using Deep Learning

This repository contains the implementation of our final year B.Tech project titled **Real-time Rendering for Cricket Shot Detection using Deep Learning**.

The project focuses on automated cricket action analysis using deep learning and computer vision. It detects cricket batting shots from real-time video sequences and recognizes umpire gestures from image data. The system was built using **MediaPipe**, **OpenCV**, **LSTM**, and **CNN** models.

---

## Project Overview

Cricket involves fast actions such as batting shots and umpire decisions. These actions are usually analyzed manually by umpires, commentators, coaches, and analysts. Manual interpretation can be subjective and may take time, especially during live matches.

This project aims to automate two important cricket analysis tasks:

1. **Cricket Shot Detection**
2. **Umpire Gesture Recognition**

The system uses computer vision and deep learning to identify batting actions and umpire signals, making it useful for cricket analytics, broadcasting, coaching, and decision-support applications.

---

## Objectives

The main objectives of this project are:

- To create a custom dataset for cricket shot detection.
- To create and use image data for umpire gesture recognition.
- To extract body, hand, and face landmarks using MediaPipe.
- To train an LSTM model for cricket shot sequence classification.
- To train a CNN model for umpire gesture classification.
- To perform real-time cricket shot detection using OpenCV.
- To support automated cricket match analysis and player performance evaluation.

---

## Problem Statement

During cricket matches, accurate decisions and real-time analysis are important. However, relying completely on manual observation for shot recognition and umpire gesture classification can be subjective and error-prone.

This project addresses the need for an automated system that can:

- Detect cricket batting shots.
- Recognize umpire gestures.
- Process real-time video input.
- Assist in cricket analysis, coaching, broadcasting, and decision-making.

---

## Features

- Real-time cricket shot detection.
- Umpire gesture classification.
- Custom dataset creation and training.
- MediaPipe-based keypoint extraction.
- LSTM-based sequence classification.
- CNN-based image classification.
- OpenCV-based video processing.
- Accuracy and performance evaluation.
- Project report and workflow documentation included.

---

## Classes Detected

### Cricket Shot Detection

The cricket shot detection model classifies the following batting actions:

- Pre Stance
- Stance
- Pull Shot
- Straight Drive

### Umpire Gesture Detection

The umpire gesture recognition model classifies the following umpire signals:

- No Action
- No Ball
- Out
- Six
- Wide
- Leg Bye
- Impact Player

---

## Methodology

The project contains two major model pipelines.

---

## 1. Cricket Shot Detection Pipeline

For cricket shot detection, real-time video frames are captured using OpenCV. MediaPipe Holistic is used to detect and extract landmarks from the player.

MediaPipe extracts landmarks from:

- Pose
- Face
- Left hand
- Right hand

The extracted keypoints are converted into numerical feature vectors. A sequence of frames is then passed into an LSTM model for action classification.

### Keypoint Extraction

For each frame, MediaPipe extracts:

- 33 pose landmarks
- 468 face landmarks
- 21 left-hand landmarks
- 21 right-hand landmarks

Each frame is converted into a feature vector of keypoint values. A sequence of 30 frames is used as input to the LSTM model.

### LSTM Model

LSTM is used because cricket shots are motion-based actions. The model learns the temporal movement pattern across multiple frames and predicts the cricket shot being played.

---

## 2. Umpire Gesture Detection Pipeline

For umpire gesture recognition, image data is used. The images are preprocessed and passed into a CNN model.

The CNN model learns visual features from umpire images and classifies them into different umpire decision categories.

### CNN Model

The CNN architecture includes:

- Convolutional layers
- ReLU activation
- MaxPooling layers
- Flatten layer
- Dense layers
- Softmax output layer

The model classifies the input image into one of the umpire gesture classes.

---

## Dataset

This repository includes the **umpire test dataset** used for testing the umpire gesture recognition model.

The project also involved custom training data for cricket shot detection and umpire gesture recognition. The training data images and project workflow are documented in the included project report.

### Dataset Categories

The umpire gesture dataset contains images from the following classes:

```text
No Action
No Ball
Out
Six
Wide
Leg Bye
Impact Player
```
The cricket shot detection dataset was created using recorded videos of batting actions such as:
Pre Stance
Stance
Pull Shot
Straight Drive

## Model Performance
The trained models achieved the following results:
| Model / Task           | Accuracy |
| ---------------------- | -------- |
| Cricket Shot Detection |   84.34% |
| Umpire Pose Detection  |    81.7% |

These results show that the proposed approach is effective for cricket action recognition and can be further improved with a larger and more diverse dataset.

## Repository Structure
real-time-cricket-shot-detection/
│
├── notebook/
│   └── project_notebooks.ipynb
│
├── dataset/
│   └── umpire_test_dataset/
│
├── files/
│   ├── project_report.pdf
│   └── workflow_diagram/
│
└── README.md

The repository contains three main folders:

1. notebook/

Contains the Jupyter Notebook files used for model building, training, testing, and implementation.

2. dataset/

Contains the umpire test dataset used for evaluating the umpire gesture detection model.

3. files/

Contains the project report, workflow diagram, and related documentation. The report includes the complete explanation of the project, model workflow, training details, architecture, results, and screenshots.

## Technologies Used
Python
OpenCV
MediaPipe
TensorFlow
Keras
NumPy
Pandas
Matplotlib
CNN
LSTM
Jupyter Notebook

## Applications

This project can be useful in:

Cricket match analysis
Sports broadcasting
Player performance analysis
Coaching assistance
Umpire decision-support systems
Automated highlight generation
Real-time sports analytics

## Limitations
Dataset size is limited.
Model accuracy may vary with lighting conditions.
Camera angle changes may affect pose detection.
Occlusion of the player or umpire can reduce prediction accuracy.
More diverse training data can improve generalization.
Real-time performance depends on hardware capability.

## Future Scope

Future improvements can include:

Adding more batting shots such as cover drive, cut shot, sweep shot, and hook shot.
Increasing the size and diversity of the dataset.
Testing on real cricket match footage.
Improving accuracy using advanced architectures.
Deploying the model as a web application.
Adding automated cricket highlight generation.
Using transformer-based models or 3D CNNs for better action recognition.
Optimizing the model for real-time edge deployment.


## Contributors

This project was developed by:

Vanagarouthu Sree Chaitran
Ashok Reddy Kurapati
C. Sujith Reddy

## Project Guide

Prof. Kalaavathi B

## Conclusion

This project demonstrates how computer vision and deep learning can be applied to real-time cricket analysis. By combining MediaPipe, OpenCV, LSTM, and CNN, the system can classify cricket batting shots and umpire gestures with promising accuracy.

The project provides a foundation for automated cricket analytics and can be extended for real-time decision support, coaching systems, match analysis, and sports broadcasting applications.



```text
Real-time cricket shot detection and umpire gesture recognition using OpenCV, MediaPipe, CNN, and LSTM.
```

