# 📘 Final Report: Smart Camera for Enhanced Security

---

## 🎯 Abstract

With rising security concerns across homes, industries, and smart cities, this project delivers a multifunctional surveillance solution powered by Raspberry Pi. Integrating face recognition, fire detection, animal intrusion monitoring, and number plate recognition, the system employs computer vision and deep learning for real-time threat response.

Key technologies include:
- YOLO-based object classification
- Haar cascades for lightweight face/fire detection
- Tesseract OCR for plate recognition
- Telegram and Flask-powered IoT alerts

The system demonstrates a scalable, cost-effective, and intelligent method to enhance personal and public safety, with future-ready expansions including Edge AI, drone surveillance, and blockchain-based privacy.

---

## 🧠 Introduction

In today's rapidly evolving landscape, conventional security methods are no longer sufficient. With the surge in urbanization and smarter infrastructure, demand has grown for surveillance systems that are not only reactive but intelligent.

This project answers that need by developing a unified system that:
- Recognizes faces for access control
- Detects fire using visual and thermal cues
- Identifies and repels animals in farmland scenarios
- Scans and validates license plates for gate automation

The heart of the system is the Raspberry Pi 4, orchestrating AI models, sensors, and actuators. Real-time alerts via IoT (Telegram bot and web dashboards) ensure users can respond instantly to intrusions or emergencies. With modular design and affordability, the solution fits a wide range of applications—from homes to agricultural fields.

---

## ⚙️ Methodology

The system consists of four core detection modules, all managed via a Raspberry Pi 4 platform using real-time video input from a Pi Camera. Each module operates independently, but integrates via shared alert channels and GPIO-based output mechanisms.

---

### 🎭 1. Face Detection

- **Framework**: OpenCV Haar Cascade (lightweight alternative to `face_recognition`)
- **Operation**: Detects frontal faces in grayscale frames, draws bounding boxes, and triggers IoT alerts if unknown faces are detected
- **Hardware**: Pi Camera, LED alert indicator

---

### 🔥 2. Fire Detection

- **Detection Method**: HSV-based color segmentation targeting red, orange, yellow hues
- **Contour Analysis**: Uses OpenCV to find fire-like regions based on color and area thresholds
- **Response**: Buzzer alert + optional image capture
- **Alternative Model**: YOLOv3 Tiny if CNN is activated

---

### 🐾 3. Animal Detection

- **Algorithm**: YOLOv3 Tiny with COCO-trained weights
- **Classes Used**: “elephant”, “cow”, “dog”, “cat”, etc.
- **Trigger**: Frame-based detection activates buzzer and sends Telegram image alert
- **Usage Scenario**: Farmlands and forest-border security

---

### 🚗 4. Number Plate Recognition

- **Image Preprocessing**: Grayscale + threshold



---

### 🔥 Fire Detection

- **Method**: HSV-based color segmentation and contour detection
- **Performance**: Rapid response to flame-like patterns, shown in testing images
- **Limitations**: Occasional false positives in high-red lighting environments

> **Detected Event**: “Fire Detected!” log + Buzzer activation  
> **Screenshot reference**: See `images/fire_test.jpg`

---

### 🐾 Animal Detection

- **Model Used**: YOLOv3 Tiny with custom classes (“elephant”, “cow”, “dog”)
- **Trigger**: Sends image via Telegram + activates buzzer
- **Success Rate**: High accuracy when detecting livestock or wild animals

> **Sample Detection Log**:


---

### 🚗 Number Plate Recognition

- **Recognition Engine**: Tesseract OCR
- **Result**: Plate `KL57R1648` correctly identified and matched to allow gate opening
- **Automation**: Servo motor engaged upon successful plate match

> **Gate Log Sequence**:


---

### 🌐 IoT Feedback Loop

Telegram bot provided instant feedback on detection modules:
- Face snapshots
- Animal intrusions
- Fire events
- Recognized vehicles

Flask server displayed real-time feed, helping debug and monitor locally.

---

### 📸 Visual Results Summary

| Module           | Screenshot Ref         | Visual Trigger     |
|------------------|------------------------|--------------------|
| Face Detection   | `face_test.jpg`        | Green boxes        |
| Fire Detection   | `fire_test.jpg`        | "Fire Detected!"   |
| Animal Detection | `animal_test.jpg`      | Label + bounding   |
| Plate Recognition| `plate_test.jpg`       | Text overlay + servo|

> Screenshots stored in `/images/` folder for demo purposes.

---