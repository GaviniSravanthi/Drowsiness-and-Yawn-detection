# 😴 Drowsiness & Yawn Detection System

A real-time **driver drowsiness and yawn detection system** using **OpenCV, Dlib, and Haarcascade**.  
This project helps monitor alertness by detecting **closed eyes (drowsiness)** and **yawning** through a webcam feed.  

---

## 📌 Features

- 👀 Detects **eye closure** using Eye Aspect Ratio (EAR).  
- 😮 Detects **yawning** using Mouth Aspect Ratio (MAR).  
- 🔔 Provides **real-time alerts** with text + optional **voice alarm**.  
- 🖥️ Works with any **webcam** (USB or laptop camera).  
- 🚗 Useful for **driver safety systems**, monitoring fatigue in operators, and health-related applications.
  
---

## ⚙️ Requirements

- Python **3.7+**  
- Webcam (built-in or external)  

### Install Dependencies

Create a virtual environment (recommended):

```bash
python -m venv venv
venv\Scripts\activate      # On Windows
source venv/bin/activate   # On Mac/Linux
pip install -r requirements.txt

```
---
### ▶️ How to Run

- Ensure haarcascade_frontalface_default.xml and shape_predictor_68_face_landmarks.dat are present.

- Run the script:

  - python drowsiness_yawn.py


- A webcam window will open showing:

  - Face with landmarks
  
  - Eye contours
  
  - Mouth contours
  
  - Alerts for drowsiness & yawning

- Press Q to quit.

### 🔍 How It Works

- Face Detection → OpenCV Haarcascade locates the face.

- Facial Landmark Detection → Dlib predicts 68 facial landmarks.

- Eye Aspect Ratio (EAR) → If eyes remain closed for >30 frames, triggers Drowsiness Alert.

- Mouth Aspect Ratio (MAR) → If mouth opens wide beyond threshold, triggers Yawn Alert.

- Voice Alerts → Uses espeak (Linux) or pyttsx3 (cross-platform) for voice messages.

### 📸 Output Example

- ✅ Eyes open → Normal

- ⚠️ Eyes closed (EAR < 0.3 for 30 frames) → Drowsiness Alert!

- 😮 Mouth wide open (MAR > 20) → Yawn Detected!


### 🚀 Future Enhancements

- Add alarm sound (beep/voice) for stronger alerts.

- Integrate with Raspberry Pi for real car monitoring.

- Add logging system to record drowsiness/yawn events.

- Deploy with a GUI dashboard for user-friendly monitoring.
  ---
  ## 📥 Download Pre-trained Model

Due to file size limits, the `shape_predictor_68_face_landmarks.dat` file is not included in this repository.  
Please download it manually from the official Dlib website:  

👉 [Download Link] (http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)  

After downloading, extract the `.bz2` file and place `shape_predictor_68_face_landmarks.dat` inside the project folder.
