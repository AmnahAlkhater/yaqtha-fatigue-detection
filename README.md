# Yaqtha – Driver Fatigue Detection System
Yaqtha is an intelligent fatigue detection system designed for industrial gate checkpoints.  
It uses computer vision techniques to analyze real-time eye behavior (EAR – Eye Aspect Ratio) and determine whether the driver is alert or fatigued.  
When fatigue is detected, the system displays an on-screen warning and sends a command to an Arduino unit to simulate the gate’s response.

---

## Project Overview
Yaqtha integrates computer vision with hardware simulation to enhance safety at factory entry points.  
The Python module detects fatigue by analyzing eye landmarks using OpenCV and MediaPipe FaceMesh.  
Upon detecting fatigue, the system triggers a red LED and buzzer through the Arduino unit, while the normal state is represented by a green LED.

---

## Features
- Real-time face and eye landmark detection  
- EAR-based fatigue calculation  
- Communication between Python and Arduino using Serial interface
- LED indicators for status  
- Buzzer alarm for fatigue  
- Fully modular (Software + Hardware layers)

---

## System Architecture
**Input Layer**  
Camera captures the driver's face in real-time.

**Processing Layer (Python – Computer Vision)**  
- Detect facial landmarks using MediaPipe FaceMesh  
- Calculate EAR (Eye Aspect Ratio)  
- Evaluate fatigue based on threshold  
- Generate status output (Normal / Fatigued)

**Communication Layer (Serial Interface)**  
- Python sends command ("G" for normal, "R" for fatigue) to Arduino via serial port

**Hardware Action Layer (Arduino Unit)**  
- "G" activates Green LED (Normal state)  
- "R" activates Red LED + Buzzer (Fatigue alert)

---

## Software (Python)
File: `fatigue_app.py`

Python script responsible for:
- Capturing camera feed  
- Detecting face landmarks  
- Calculating EAR  
- Determining fatigue  
- Sending signals (R/G) to Arduino  

---

## Hardware (Arduino)
File: `fatigue_gate.ino`

Arduino sketch performs:
- Reading serial commands  
- Activating Green/Red LEDs  
- Triggering buzzer on fatigue  

---

## Technologies Used
- Python 3  
- OpenCV  
- MediaPipe FaceMesh  
- NumPy  
- PySerial  
- Arduino Uno 

---

## How to Run
### 1) Install dependencies:
```bash
pip install opencv-python mediapipe numpy pyserial
```
### 2) Run Python script:
```bash
python fatigue_app.py
```
### 3) Upload Arduino code:
Open `fatigue_gate.ino` in Arduino IDE and upload it.

---
## Author

**Amnah Alkhater**  
Lead Developer and Technical Owner of the Yaqtha Fatigue Detection Project

LinkedIn: https://www.linkedin.com/in/amnahalkhater
