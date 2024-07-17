# Smart Glasses for Blinds

## Project Aims

The Smart Glasses for Blinds project aims to develop an effective and comfortable solution for enhancing the interaction between visually impaired individuals and their surroundings. The core objective is to improve the quality of life for blind individuals, making their experiences comparable to those of sighted people.

## Project Overview

In our proposed system, a camera is integrated into the glasses worn by the blind user. This camera captures the scene around the user, including faces of people and surrounding objects. The system then informs the user about the identities of people and objects in front of them. Face recognition and object detection are performed using a pre-built dataset.

## How It Works

1. **User Interaction**: The user (blind person) initiates the process by clicking a button on the glasses.
2. **Image Capture**: The camera captures an image upon the user's action and sends it to the microcontroller.
3. **Cloud Processing**: The microcontroller transmits the image to the cloud, where data normalization and face/object recognition are performed.
4. **Audio Feedback**: The recognized information is sent back to the microcontroller, which converts the text to audio. This audio output is then relayed to the user through headphones.

## Requirements and Analysis

### Software

#### Face Recognition Steps:
1. Detect faces in an image.
2. Identify faces despite variations in orientation and lighting.
3. Extract unique facial features.
4. Compare features with known faces to identify individuals.

#### Example Code for Face Recognition:
```python
import face_recognition

# Load the image
image = face_recognition.load_image_file("your_file.jpg")
face_locations = face_recognition.face_locations(image)

# Recognize known faces
known_image = face_recognition.load_image_file("biden.jpg")
unknown_image = face_recognition.load_image_file("unknown.jpg")
biden_encoding = face_recognition.face_encodings(known_image)[0]
unknown_encoding = face_recognition.face_encodings(unknown_image)[0]
results = face_recognition.compare_faces([biden_encoding], unknown_encoding)

### Object Detection Steps:
Break the image into overlapping tiles.
Process each tile using a neural network.
Compile results from all tiles.
Downsample the compiled data for final object detection.

Hardware Design and Components:
Raspberry Pi 3 B+
Camera module
3D-printed glasses frame
Battery or power bank
Breadboard and cables
Headphones
Button
Heatsink
Testing
Hardware Testing:
Unit tests for individual components like the camera, button, and audio output.
System integration tests to ensure all components work together seamlessly.
Software Testing:
Verify software meets planned requirements and responds correctly to various inputs.
Ensure acceptable performance, usability, and compatibility with intended environments.
This README provides a comprehensive overview of the Smart Glasses for Blinds project, detailing its aims, functionality, and the technical steps involved in both software and hardware components.
