# 🚦 AI-Powered Smart Toll Management System

An **AI-driven Computer Vision system** designed to automate toll booth traffic management using real-time vehicle detection and queue analysis.

Built with **YOLOv8 and OpenCV**, the system monitors vehicle density at toll gates and automatically triggers a **traffic release mechanism** when congestion crosses a predefined threshold.

This helps reduce **traffic gridlocks, human dependency, and inefficient toll operations.**

---

<p align="center">
<img src="working/demo.gif" width="700"/>
<br>
<em>Real-time vehicle detection and congestion monitoring using YOLOv8</em>
</p>

---

# 🌍 Problem Statement

Traditional toll booths rely on:

• Manual supervision
• Pressure sensors
• Static vehicle counters

These systems **cannot visually measure queue density** and often fail during high-traffic scenarios.

This project introduces a **Computer Vision based traffic monitoring system** that dynamically detects congestion and triggers automated toll release logic.

---

# 💡 Key Innovations

### 🟡 Virtual Boundary Detection

A digital **"Yellow Line"** acts as a virtual toll gate boundary.

Vehicles crossing this line are considered **part of the the queue.**

---

### 🚗 Real-Time Traffic Density Analysis

Instead of simply counting vehicles, the system calculates how many vehicles are **occupying the congestion zone** at any moment.

---

### ⚡ Automated Toll Release Logic

When the queue exceeds a predefined threshold, the system automatically triggers:

**"RELEASE TOLL BOOTH"**

This can be integrated with **real-world gate control hardware.**

---

# 🧠 System Architecture

```
Video Input
     │
     ▼
YOLOv8 Vehicle Detection
     │
     ▼
Vehicle Class Filtering
     │
     ▼
Queue Zone Detection (Yellow Line)
     │
     ▼
Vehicle Density Calculation
     │
     ▼
Threshold Trigger
     │
     ▼
🚦 Toll Release Signal
```

---

# 🛠️ Tech Stack

### AI Model

YOLOv8 (Ultralytics)

### Programming Language

Python 3.x

### Libraries

• ultralytics — Object detection engine
• OpenCV — Video processing
• cvzone — Visualization utilities
• NumPy — Numerical processing
• math — Confidence calculation

---

# 🚀 How It Works

## 1️⃣ Vehicle Detection

The system loads the **YOLOv8n model**, trained on the COCO dataset.

Only relevant classes are detected:

• Cars
• Trucks
• Buses
• Motorbikes

All irrelevant objects are filtered.

---

## 2️⃣ Spatial Mapping

A **virtual toll boundary** is defined:

```
yellow_line_y = 450
```

Each vehicle's **centroid (cx, cy)** is tracked.

If:

```
cy > yellow_line_y
```

The vehicle is considered **inside the queue zone.**

---

## 3️⃣ Queue Monitoring Logic

The system continuously:

• Tracks vehicles crossing the boundary
• Counts vehicles in the congestion zone

Decision logic:

```
If Queue Count < Threshold
Status = Normal
```

```
If Queue Count >= Threshold
Status = RELEASE TOLL BOOTH
```

---

# 📊 Real-Time Visualization

The UI provides clear visual feedback.

### 🔵 Blue Bounding Boxes

Detected vehicles

### 🔴 Red Bounding Boxes

Vehicles inside congestion zone

### 📡 HUD Panel

Displays:

• Current queue count
• Toll release status

---

# ⚙️ Installation

Clone the repository

```bash
git clone https://github.com/Pranav260804/Toll-Booth-Traffic-Management-AI.git
```

Navigate into project

```bash
cd Toll-Booth-Traffic-Management-AI
```

Install dependencies

```bash
pip install ultralytics opencv-python cvzone
```

---

# ▶️ Running the Project

```bash
python traffic_high.py
```

or

```bash
python traffic_low.py
```

The system will start detecting vehicles and monitoring congestion in real time.

---

# 📸 Demo

<p align="center">
<img src="working/demo.gif" width="700">
</p>

---

# 🔮 Future Improvements

### 🚘 Vehicle Tracking

Integrate **DeepSORT** to assign unique IDs to vehicles.

### 🔎 License Plate Recognition

Add **Automatic Number Plate Recognition (ANPR)** for vehicle identification.

### ☁️ Cloud Analytics

Send traffic data to a cloud dashboard for:

• traffic analysis
• city planning
• congestion prediction

---

# 🌐 Potential Applications

• Smart City Infrastructure
• Highway Toll Management
• Traffic Congestion Monitoring
• Intelligent Transport Systems

---

# 👨‍💻 Author

**Pranav Kale**

AI / Computer Vision Enthusiast
Computer Engineering (AI/ML)

GitHub
https://github.com/Pranav260804

LinkedIn
(Add your LinkedIn profile link here)

---

# 🤝 Credits

Initial development reference from **apuProgramz**

---

# ⭐ Support

If you found this project useful:

⭐ Star the repository
🍴 Fork the project
📢 Share with others

