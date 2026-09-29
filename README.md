# 🚗 Real-Time ADAS System

A fully browser-based Advanced Driver Assistance System (ADAS) that integrates **three AI models** running simultaneously at **25+ FPS** — with no backend, no server, and no installation.

![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![FPS](https://img.shields.io/badge/FPS-25%2B-blue)
![License](https://img.shields.io/badge/License-MIT-yellow)
![OpenCV](https://img.shields.io/badge/OpenCV.js-4.8.0-red)
![YOLO](https://img.shields.io/badge/YOLOv8-ONNX-orange)
![MediaPipe](https://img.shields.io/badge/MediaPipe-FaceMesh-green)

---

## ✨ Features

### 🚗 Real-Time Lane Detection
- Left & Right lane tracking with curved lane support
- Perspective Transform (Bird's Eye View)
- HSV color segmentation (white + yellow markings)
- Sliding Window Algorithm + 2nd-degree Polynomial Curve Fitting
- Lane Departure Warning (LDW) with visual + audio alerts

### 🛣️ Intelligent Driver Guidance
- Lane center offset calculation
- Road curvature radius estimation
- Steering angle suggestion (front-wheel estimate)
- Turn hint with distance to upcoming curve

### 🚙 AI-Powered Object Detection
- Real-time detection of cars, pedestrians, and bikes
- Lane-aware classification ("Car ahead in your lane")
- Bounding boxes with confidence scores
- Forward collision warning

### 😴 Driver Drowsiness Detection
- 468 facial landmarks tracked in real-time
- Eye Aspect Ratio (EAR) based blink detection
- Yawn detection (Mouth Aspect Ratio)
- Real-time drowsiness alarm

### 🌙 Low-Light Enhancement
- Adaptive brightness detection
- Gamma correction + CLAHE (Contrast Limited Adaptive Histogram Equalization)
- Custom fallback for unsupported OpenCV.js builds

### 📊 Live HUD & Visualization
- Bird's Eye View lane mask
- FPS counter + performance metrics
- Speed, offset, curvature display
- Multi-camera layout (road + driver)

---

##  Tech Stack

| Category | Technology |
|----------|-----------|
| **Computer Vision** | OpenCV.js (WASM) |
| **Object Detection** | YOLOv8 + ONNX Runtime (WebGPU + WASM) |
| **Face Detection** | MediaPipe FaceMesh |
| **Architecture** | Web Worker (parallel processing) |
| **Frontend** | HTML5 Canvas, JavaScript, CSS3 |
| **Audio** | Web Audio API |
| **Deployment** | Browser-based (no backend) |


## Getting Started

### Prerequisites
- Modern browser (Chrome, Edge, or Firefox)
- Python 3.x (for local server)
- Webcam (for driver monitoring)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/adas-system.git
   cd adas-system

   http://localhost:5501/a.html

   How It Works
   
   1. Lane Detection Pipeline
   
   Video Frame
    ↓
Grayscale Conversion + Canny Edge Detection
    ↓
HSV Color Segmentation (White + Yellow)
    ↓
Mask Fusion + Morphological Cleaning
    ↓
Perspective Transform (Bird's Eye View)
    ↓
Sliding Window Algorithm
    ↓
2nd-degree Polynomial Curve Fitting
    ↓
Temporal Smoothing (5-frame window)
    ↓
Inverse Perspective Projection
    ↓
Lane Overlay + LDW

2. Object Detection Pipeline

Video Frame
    ↓
Resize to 640x640 + Normalize
    ↓
YOLOv8 Inference (ONNX Runtime)
    ↓
Non-Maximum Suppression
    ↓
Lane Classification (in-lane check)
    ↓
Bounding Box Rendering
    ↓
Forward Collision Warning

3. Driver Drowsiness Pipeline

Driver Camera Frame
    ↓
Web Worker: MediaPipe FaceMesh
    ↓
468 Facial Landmarks
    ↓
Eye Aspect Ratio (EAR) Calculation
    ↓
Blink Detection + Yawn Detection
    ↓
Drowsiness Alarm

 **Performance** 
Metric	Value
FPS	25+ (all modules running)
Resolution	480x360 (processing)
Lane Detection	Real-time
Object Detection	2 FPS (throttled to every 5th frame)
Face Detection	8 FPS (throttled)

Optimization Techniques
✅ OpenCV Mat memory management

✅ Threshold bounds caching

✅ Frame throttling (YOLO every 5th frame)

✅ Web Worker for FaceMesh

✅ Custom CLAHE fallback

✅ Conditional canvas resizing

 Future Enhancements
□ Traffic sign detection
□ Traffic light detection
□ Kalman Filter for lane prediction
□ Lane change prediction
□ Night vision enhancement
□ Mobile app (React Native)

Author
Aditya Prasad

GitHub: Aditya123286

LinkedIn:  linkedin.com/in/aditya-prasad-77a941318


 Acknowledgments
OpenCV.js — Computer Vision library

ONNX Runtime Web — Deep Learning inference

Ultralytics YOLOv8 — Object detection model

MediaPipe — Face detection framework


 Show Your Support
If this project helped you, please give it a ⭐ star!

