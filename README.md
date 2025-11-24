# 🚗 Real-Time Driver Drowsiness & Emotion Detection System  

A real-time AI–driven driver safety system that monitors **drowsiness**, **facial emotions**, **yawn detection**, **blink frequency**, and **gaze estimation** to prevent accidents and enhance alertness.

---

# 📌 Overview

Reaching Level-4 autonomous driving requires advanced driver attention monitoring.  
Many road accidents occur due to:

- 😴 Eye closure from tiredness  
- 🥱 Yawning and fatigue  
- 😔 Emotional distress affecting focus  

To address this, we built a **CNN + Dlib based real-time drowsiness detection system** that alerts the infotainment system and suggests nearby refreshment spots.

---

# 🌟 Key Features

## 💤 **1. Real-Time Drowsiness Detection**
Uses **EAR (Eye Aspect Ratio)** with a threshold of **0.15** to detect when eyes close beyond normal blinking.

## 😮 **2. Yawn Detection**
CNN-based lightweight classifier detects mouth opening patterns indicating fatigue.

## 😊 **3. Emotion Recognition**
Detects emotions like:
- Happy  
- Angry  
- Sad  
- Neutral  
- Tired  

System recommends actions based on driver mood.

## 🎯 **4. Eye Gaze Estimation**
A custom attention-based CNN trained on **NVGaze 2M dataset**  
➡ Achieves **0.5° best-case accuracy** across the FOV.

## 🔊 **5. Infotainment Voice Alerts**
If the driver is drowsy:
- Car triggers alarm  
- Infotainment recommends nearby cafés, rest areas, hotels  

## 🚘 **6. Real-Time Processing**
Runs **live** using:
- Webcam  
- On-board camera  
- Raspberry Pi / Laptop  

---

# 🧱 Tech Stack

## 🧠 **Machine Learning**
| Technology | Purpose |
|-----------|---------|
| **CNN (Convolutional Neural Network)** | Yawn detection + Emotion detection |
| **Attention Mechanism CNN** | Eye gaze estimation |
| **Lightweight CNN Sub-network** | Blink & EAR-based drowsiness detection |
| **NVGaze 2M Dataset** | Gaze estimation training |

---

## 👁️ **Computer Vision**
| Library | Usage |
|--------|-------|
| **Dlib** | Facial landmarks, EAR computation |
| **OpenCV** | Frame capture, preprocessing, drawing |
| **Mediapipe** | (Optional) Extended emotion/gesture support |

---

## 🧮 **Algorithms Used**

### ✔ EAR (Eye Aspect Ratio)  
A proven method to detect eye closure:

```
EAR = (||p2 - p6|| + ||p3 - p5||) / (2 * ||p1 - p4||)
```

Threshold used: **0.15**  
If EAR < 0.15 for continuous frames → Driver is drowsy.

---

# ⚙️ System Operation

## 🔍 **Step-by-step pipeline**

1. **Capture video frames** from the camera  
2. **Detect face** using HOG/CNN  
3. **Extract 68 facial landmarks** using Dlib  
4. **Compute EAR** to detect drowsiness  
5. **Run CNN model** for yawning & emotion recognition  
6. **Estimate gaze direction** using attention-based CNN  
7. If drowsy →  
   - 🔊 Send voice alert  
   - 🗺️ Recommend nearby refreshment places  
8. If sad/angry → system suggests mood-based actions (music, break, meditation etc.)

---

# 🔔 Alerts & Recommendations

When drowsiness detected:
- “⚠️ Driver is drowsy, please take a break!”
- Infotainment screen shows nearest:
  - Cafes  
  - Rest stops  
  - Restaurants  
  - Hotels  
  - Fuel stations  

---

# 📈 Model Performance

| Component | Accuracy |
|----------|----------|
| CNN + Dlib Drowsiness Model | **91.6%** |
| Yawn Detection CNN | **89–92%** |
| Emotion Recognition | **85–90%** |
| Eye Gaze Estimation | **0.5° best-case accuracy** |

---

# 🛠 Installation

```bash
git clone https://github.com/your-username/drowsiness-detection.git
cd drowsiness-detection
pip install -r requirements.txt
python main.py
```



