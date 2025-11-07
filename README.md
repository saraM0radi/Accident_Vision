# 🚗 Accident Detection from Video using Deep Learning

## 📌 Project Overview
Accident detection from video footage is a critical computer vision application that can reduce emergency response time.  
This project builds a **binary video classification model** that predicts whether an accident occurred in a short video clip (a few seconds to tens of seconds long).

The dataset consists of **short video clips represented as sequential frames**, and the model analyzes temporal and motion-based features to detect accidents.

---

## 🔍 Method Highlights
Our approach extracts both spatial and motion-based representations:

- ✅ **Optical Flow** is used to capture motion changes between frames  
- ✅ **Divergence Masks** are applied to highlight areas with sudden motion changes (e.g., collision impact regions)  
- ✅ **Feature extraction** is performed using **ResNet50**
- ✅ **Temporal sequence modeling** is handled using **GRU (Gated Recurrent Unit)**
- ✅ Final architecture: **ResNet50 + GRU**
- ✅ Achieved **85% test accuracy**

---

## 📂 Dataset Description

### 🎥 Video Format
- Each video is a short clip composed of many sequential frames
- Frames are extracted at **fixed time intervals** (few milliseconds apart)
- Extracted frames are processed to generate:
  - Raw frame features
  - Optical flow maps
  - Divergence masks

### 🧾 Metadata Columns
| Column | Description |
|--------|------------|
| `time_of_event` | Timestamp of accident (NaN if no accident occurred) → **Used for labeling** |
| `time_of_alert` | Emergency alert timestamp |
| `light_conditions` | Lighting conditions (Day, Night, etc.) |
| `weather` | Weather condition |
| `scene` | Road/environment type |
| `time_to_accident` | Time before accident happens |

### ✅ Label Rule
time_of_event != NaN → Accident (1)
time_of_event == NaN → No Accident (0)

---

## 🎯 Goal
Develop a **binary classifier** that:
- Takes sequential video frames as input
- Learns motion and appearance patterns
- Predicts:
  - `1` → Accident detected
  - `0` → No accident detected

---

## 📜 License
This project is intended for educational and research purposes.
