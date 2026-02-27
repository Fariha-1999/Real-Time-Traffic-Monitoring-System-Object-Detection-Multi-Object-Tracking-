# Real-Time Traffic Monitoring System (Object Detection + Multi-Object Tracking)

This project implements a **real-time traffic monitoring system** with vehicle detection, multi-object tracking, and a live GUI for performance monitoring.

---

## 📝 Overview

- Detects multiple vehicle types in HD video streams using a fine-tuned **YOLOv8/YOLO26s model**.  
- Tracks vehicles across frames with **ByteTrack**, maintaining unique IDs even under occlusion.  
- Displays live bounding boxes, class labels, tracking IDs, confidence scores, and per-class vehicle counts.  
- Monitors system performance: **FPS**, CPU/GPU usage, and memory consumption.  
- Generates fully annotated video outputs and structured logs for evaluation.

---

## ⚙️ Features

- **Model Fine-Tuning:** Trained YOLO on a custom dataset (462 images) of traffic scenarios. For now its manually annotated in roboflow.  
- **Multi-Object Tracking:** Persistent ID assignment using ByteTrack with soft confidence filtering.  
- **GUI & Metrics:** Live visualization of detections with performance dashboard and start/stop controls.  
- **Resource Optimization:** Supports real-time inference on limited GPU hardware.  
- **Experiment Logging:** Logs predictions, counts, and metrics in structured JSON/CSV formats.

---

## 📊 Performance Metrics

- Real-time inference with **FPS monitoring**  
- Per-class vehicle counts  
- CPU/GPU utilization logging  
- Optional **ONNX/TensorRT optimization** for maximum throughput  

---
<!--
## 🎥 Demo

**Annotated Video Output Example:**

- Bounding boxes with class names, confidence scores, and tracking IDs  
- Live FPS overlay  
- Per-class vehicle counts on the video feed  

*(Replace with GIF or MP4 demo in your repo for better visualization)*  

---
-->
## 💻 Tech Stack

- **Frameworks:** PyTorch, Ultralytics YOLO, OpenCV  
- **Tracking:** ByteTrack  
- **Monitoring:** psutil for CPU/GPU/RAM

---

## ⚡ Optimization Strategies

- **Low-Batch Training:** Handled GPU memory limits by gradient accumulation and batch size tuning  
- **Mixed Precision Training:** FP16 to reduce memory consumption  
- **Persistent Tracking:** ByteTrack keeps unique IDs across frames and resolves occlusions  
- **Soft Confidence Thresholds:** Avoids premature filtering of weak detections
- ONNX/TensorRT for model optimization  
