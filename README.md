# Pendulum Tracking with OpenCV

[![Python 3.7+](https://img.shields.io/badge/Python-3.7%2B-blue.svg)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-2-green.svg)](https://opencv.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A program for the automated analysis of the motion of a mathematical pendulum using computer vision. It tracks oscillations, calculates coordinates, and plots a graph of coordinates on time.

## Capabilities

-  Automatic object detection from video
-  Object recognition from a reference image using ORB descriptors
-  Calculating the coordinates of the object's center in each frame
-  Plotting graphics based on X coordinates over time
-  Converting pixel coordinates to centimeters
-  Previewing damped oscillations

## Working Principle
### 1) Object Detection
Applying Gaussian blur to reduce noise and image binarization using threshold Finding contours using cv2.findContours()

### 2) Object Recognition
Using ORB for feature extraction, matching with a reference image and selecting the best match

### 3) Motion Tracking
Calculating the object's center in each frame and converting coordinates to centimeters

### 4) Visualization
Plotting X(t)

## Calibration parameters
- Coordinates system is based on the ball size, so ball_size should be changed for every different object.
- For different objects user should use different binary_color_divergence coefficient for better object detecting.
- If object is too small, user should change size boundaries in find_coordinates_of_the_ball function
  
## Visualisation
<img width="1536" height="850" alt="80image" src="https://github.com/user-attachments/assets/f21ca93d-4e7a-45ca-945b-aa9ea21b50e8"/>
There is a notable detail on the image: the pendulum oscillates in several axes, so the "main" damped oscillation also oscillates.
For a 10 minute video processing time is 20-30 minutes.

## Possible improvements
- Comparison between theoretical solution of a differential equation with calculated resistance coefficient and practical result
- Several objects tracking
- Oscillation period calculation
- CSV export
- Convenient UI
- Several axes analysis

## Research version
A small research dedicated to the comparison of live tracking and theoretical solution using the runge kutta 4th order method resulted into a graph:
The first image is for 0.47 air resistance coefficient and the second is for 0.7 coefficient
<img width="1200" height="600" alt="80+simulation" src="https://github.com/user-attachments/assets/5d8eef6d-af3e-452a-bcca-1d7758156538" />
<img width="1200" height="600" alt="80 simulation 0 7" src="https://github.com/user-attachments/assets/72b2a581-d138-4462-b23f-2825fbd6d73f" />

Model does not include linear friction in the pendulum, string resistance, dynamic air resistance coefficient and complicated moment of inertia of the ball. This may be the reason of stronger oscillation damping.
## Contact information

Email: orovor9@gmail.com
