# 📦 Household Object Recognition & Visual Explainability (YOLO11 + ArtAug)

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)
[![YOLO11](https://img.shields.io/badge/Model-YOLO11n-orange)](https://github.com/ultralytics/ultralytics)
[![Framework](https://img.shields.io/badge/UI-Gradio-red)](https://gradio.app/)

Computer Vision Assignment 2 repository for Astana IT University. Upgrading baseline object recognition models using State-of-the-Art (SOTA) YOLO11, artistic augmentations (ArtAug), interactive Gradio UI, and explainability heatmaps.

---

## 🎯 Project Overview
* **Domain:** Household Object Detection (`bottle`, `cup`, `keys`, `pen`)
* **Total Dataset:** 541 images (414 A1 baseline + 127 ArtAug synthetic frames)
* **SOTA Architecture:** YOLO11n (Ultralytics)
* **Training Setup:** 50 Epochs on NVIDIA Tesla T4 GPU (Google Colab)

---

## 📊 Performance Metrics

| Metric | Baseline (Assignment 1) | SOTA (Assignment 2) | Improvement ($\Delta$) |
| :--- | :--- | :--- | :--- |
| **mAP@0.5** | 84.20% | **97.05%** | **+12.85%** |
| **mAP@0.5:0.95** | 71.50% | **89.46%** | **+17.96%** |
| **Inference Latency** | 28.5 ms | **16.20 ms** | **-12.3 ms** |
| **Frame Rate (FPS)** | 35.0 FPS | **38.85 FPS** | **+3.85 FPS** |

### Class-wise Performance:
* 🍾 **Bottle:** 99.5% mAP@0.5
* ☕ **Cup:** 92.4% mAP@0.5
* 🔑 **Keys:** 96.8% mAP@0.5
* ✏️ **Pen:** 99.5% mAP@0.5

---

## 💻 Interactive Web Application & Explainability

The project includes an interactive web interface powered by **Gradio** featuring:
1. **Real-time Prediction:** Bounding box detection with confidence scoring.
2. **Visual Explanation:** Attention Heatmap overlays (JET colormap) showing feature activations.
3. **Latency Benchmarking:** Real-time hardware performance tracking.

> **Note on App Deployment:** The Gradio demo is hosted via Google Colab temporary sessions. To launch the interactive web interface, open and run the notebook `Assignment2_YOLO11.ipynb`.

---

## 🔬 Failure Analysis (Model Limitations)
During out-of-distribution (OOD) testing, systematic misclassifications were identified:
* **Ceramic Cup / Keys identified as `bottle`:** Due to vertical aspect ratios and specular highlights, the model exhibits a slight bias towards the dominant `bottle` class geometry. Detailed activation heatmaps are included in the official report.

---

## 🛠️ How to Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/ayashyaa/CV_Assignment2_YOLO11.git](https://github.com/ayashyaa/CV_Assignment2_YOLO11.git)
   cd CV_Assignment2_YOLO11

2. **Install dependencies:**
   ```bash
   pip install ultralytics roboflow gradio opencv-python

3. **Run Notebook:**
   ```bash
   Assignment2_YOLO11.ipynb
