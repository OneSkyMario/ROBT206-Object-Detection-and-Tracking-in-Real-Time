# ROBT206-Object-Detection-and-Tracking-in-Real-Time
Real-time object detection and tracking: a YOLOv5-powered Python app captures people via USB camera, sends averaged 2D coords over serial to an Arduino Nano, which drives pan–tilt HS-225MG servos and a laser pointer in a 3D-printed mount, ensuring smooth, jitter-free target locking.

## 🚀 Features
- **Real-time Detection**: YOLOv5s model running on a PC captures people in the video stream (≥ 0.2 confidence).  
- **Smooth Tracking**: A 5-frame moving average buffer and proportional stepping keep servo motion fluid and avoid jitter.  
- **Pan–Tilt Rig**: Custom 3D-printed mount for camera + laser, driven by two micro-servos on an Arduino Nano.  
- **Laser Highlighting**: “Scan” and “Track” modes—laser pointer toggles via serial commands (`H`/`L`) to mark the target in 3D space.  
- **Modular Design**: Python ↔ Arduino comms over serial (`dx,dy\n`), making it easy to swap in different CV models or actuator platforms.


# Requirements 

## 🛠 Hardware
- **Arduino Nano**  
- **2× HS-225MG Servo Motors** (Pan & Tilt)  
- **USB Webcam**  
- **SunFounder Laser Module**  
- 3D-printed pan-tilt mount (CAD + STL in `mount/`)

## 💻 Software Stack
- **Python 3.8+**  
  - `torch`, `ultralytics` (YOLOv5)  
  - `opencv-python` for video capture & annotation  
  - `pyserial` for Arduino comms  
- **Arduino IDE**  
  - Servo library for motion control  
  - Simple serial parser for `dx,dy` commands  

YOLOv5: https://pytorch.org/hub/ultralytics_yolov5/

## Demo
https://drive.google.com/file/d/13Rfjn-wCp4zZR4Br-RrTB7L84GVSeRFl/view?usp=sharing
