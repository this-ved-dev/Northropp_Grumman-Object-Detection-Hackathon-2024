# Northrop Grumman Object Detection Hackathon 2024

A comprehensive object detection system developed for the Northrop Grumman Hackathon 2024, featuring a multi-model ensemble approach with real-time and static image analysis capabilities.

## 🚀 Overview

This project implements a versatile object detection platform that leverages state-of-the-art deep learning models to identify and localize objects in both uploaded images and real-time video streams. The system integrates multiple architectures, including YOLOv8, YOLOv7, and OWL-ViT, providing a robust and flexible solution for various computer vision tasks.

## ✨ Key Features

- **Multi-Model Support**: Switch between YOLOv8, YOLOv7, and OWL-ViT (Grounding DINO) dynamically.
- **Ensemble Detection**: A unique "Combined" mode that merges detections from YOLOv7 and OWL-ViT using Intersection over Union (IoU) logic for enhanced accuracy.
- **Real-Time Analysis**: Stream video from a webcam and receive low-latency annotated frames via WebSockets (SocketIO).
- **Static Image Processing**: Upload images for detailed analysis with confidence score reporting and visual annotations.
- **Modern Web Interface**: Clean, responsive UI featuring professional Northrop Grumman branding, real-time feedback, and confidence level badges.

## 🛠️ Tech Stack

- **Backend**: Python, Flask, Flask-SocketIO
- **Frontend**: HTML5, CSS3, Vanilla JavaScript, Socket.io
- **AI/ML**: PyTorch, Ultralytics (YOLOv8), Hugging Face Transformers (OWL-ViT/OwlViT), YOLOv7
- **Computer Vision**: OpenCV, PIL, NumPy

## 📂 Repository Structure

```text
├── models/             # Model weights (e.g., yolov8n.pt)
├── static/             # CSS, images, and other static assets
├── templates/          # HTML templates (upload.html, real-time.html)
├── constants.py        # Configuration and custom detection labels
├── helper.py           # Utility functions for IoU and detection merging
├── real-time.py        # Flask application for real-time video detection
├── upload-image.py     # Flask application for static image upload detection
└── README.md           # Project documentation
```

## ⚙️ Installation & Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-repo/Northropp_Grumman-Object-Detection-Hackathon-2024.git
   cd Northropp_Grumman-Object-Detection-Hackathon-2024
   ```

2. **Install dependencies**:
   ```bash
   pip install flask flask-socketio opencv-python ultralytics torch transformers pillow
   ```

3. **Run the Static Image Upload App**:
   ```bash
   python upload-image.py
   ```
   Access at `http://localhost:5001`.

4. **Run the Real-Time Detection App**:
   ```bash
   python real-time.py
   ```
   Access at `http://localhost:5000`.

## 🧠 Methodology

The system's core strength lies in its ability to combine different detection paradigms:
- **YOLO (You Only Look Once)**: Used for fast, high-performance detection of common object classes.
- **OWL-ViT (Open-World Localization)**: Provides zero-shot localization capabilities for custom or rarer labels defined in `constants.py`.
- **Merging Logic**: The `merge_detections` function in `helper.py` uses an IoU threshold (default 0.5) to reconcile overlapping detections from different models, prioritizing the highest confidence score.

---
*Developed for the Northrop Grumman Hackathon 2024.*
