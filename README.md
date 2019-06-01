#### This repo is still a Work in Progress.

## Object detection and object motion prediction 
The goal is to detect cars in a video. Once the cars are detected then predict the path of all the detected cars.

### Detection
For detection YOLO is used. 
The input video is divided into individual frames and yolo is run on each frame.

### Prediction
The plan is to use Kalman filter on each of the detected objects (i.e. Cars). Here are the steps:
* Create a state for the objects to track. This would include x_pos, y_pos.
* Come up with a motion model that would closely represent the vehicle motion in the video frame.
* Each frame would represent a measurement, so on arrival of each frame run the Kalman filter predict cycle and update cycle.
* Tracks needs to be created for each new car that is detected. If the detected car is not a new car then association needs to be done.
* Predict step also needs to be run with some larger value of time (t) to come up with an estimated trajectory of car.
* Show the trajectory on the image 

References :
[Gentle guide on how YOLO Object Localization works with Keras](https://heartbeat.fritz.ai/gentle-guide-on-how-yolo-object-localization-works-with-keras-part-2-65fe59ac12d)
