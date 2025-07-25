notepad setup.md
# 🔧 Setup Guide: Smart Camera Surveillance System

Welcome to the setup guide for the **Smart Camera for Enhanced Security**—a Raspberry Pi–based multifunctional surveillance system integrating Face Detection, Fire Detection, Animal Detection, and Number Plate Recognition.

---

## 🛠️ Hardware Requirements

- Raspberry Pi 4 Model B (1GB / 2GB / 4GB RAM)
- Pi Camera Module (5MP, MIPI CSI interface)
- Servo Motor (Tower Pro SG90)
- 7805 Voltage Regulator
- Buzzer
- LEDs for status indicators
- Breadboard, jumper wires
- Power supply (USB-C, 5V 3A)
- Optional: PIR sensors, external display, microphone

---

## 💻 Software Requirements

- Python 3.9+
- Raspbian OS / Raspberry Pi OS
- DipTrace for PCB design (optional)
- Telegram Bot API (for IoT alerts)
- Flask (for web interface)
- VNC Viewer (remote control)
- Required Python packages:
  ```bash
  pip install -r requirements.txt