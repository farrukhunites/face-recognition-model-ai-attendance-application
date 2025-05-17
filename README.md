# 🤖 Face Recognition Model for AI Attendance Application

This repository contains the **face recognition AI model** developed specifically for the **AI Attendance Backend** system. The model enables accurate detection and identification of faces from live video frames to automate attendance marking in classroom or workplace environments.

---

## 🎯 Purpose

To build a robust and efficient face recognition pipeline that can detect multiple faces in real-time, extract meaningful features, and accurately identify enrolled users. The model is designed to be integrated seamlessly as a standalone executable with the Django backend.

---

## 🏗️ Architecture Overview

The face recognition pipeline consists of three key stages:

### 1. Face Detection with YOLO

- The system first applies **YOLO (You Only Look Once)**, a state-of-the-art real-time object detection algorithm, to detect faces in each frame.
- YOLO provides bounding boxes around every face present in the image, enabling multi-face detection even in crowded classroom settings.
- YOLO’s high speed and accuracy make it suitable for processing live video streams without significant latency.

### 2. Feature Extraction with FaceNet

- For each detected face, the model extracts a fixed-length, 128-dimensional **embedding vector** using the **FaceNet** model.
- FaceNet maps facial images to a compact feature space where distances directly correspond to face similarity.
- These embeddings are highly discriminative and robust to variations in lighting, pose, and expression.

### 3. Face Classification with SVM

- The extracted embeddings serve as input features to a **Support Vector Machine (SVM)** classifier.
- The SVM is trained on labeled embeddings of enrolled students, learning to distinguish among different individuals.
- During inference, the SVM predicts the identity of each detected face based on its embedding.
- This step provides the final recognized identity for attendance marking.

---

## 🧱 Tech Stack & Tools

- **YOLO** – Real-time face detection  
- **FaceNet** – Deep neural network for facial embedding extraction  
- **SVM (Support Vector Machine)** – Classifier for face recognition  
- **OpenCV** – Image processing and frame handling  
- **Python** – Implementation language  
- **PyInstaller** – Packaging model as standalone executable  

---

## 🗂️ Project Structure (Simplified)

```

face-recognition-model-ai-attendance-application/
├── data/                 # Training images and datasets
├── model/                # Trained SVM model and FaceNet embeddings
├── src/                  # Detection, embedding, classification code
├── train.py              # Training pipeline for SVM classifier
├── infer.py              # Inference pipeline combining YOLO, FaceNet, and SVM
├── build\_model.sh        # Script to package model into ai\_model.exe
├── requirements.txt      # Dependencies
└── README.md             # This file

```

---

## 🔍 Testing the Model

You can test this face recognition model through the full **AI Attendance Backend** and **Frontend** applications:

- Backend Repository: [https://github.com/farrukhunites/ai_attendance_backend](https://github.com/farrukhunites/ai_attendance_backend)  
- Frontend Repository: [https://github.com/farrukhunites/ai_attendance_frontend](https://github.com/farrukhunites/ai_attendance_frontend)  

The backend communicates with this model via the packaged executable (`ai_model.exe`) for real-time face detection and recognition during attendance marking. The frontend allows users and admins to interact with the system and view attendance history.

---

## 🙌 Contributions

Contributions to improve detection accuracy, optimize performance, add features, or enhance integration are highly welcome!  

If you'd like to contribute:  
- Fork the repository  
- Make your changes in a feature branch  
- Open a Pull Request (PR) with a clear description of your improvements  

We appreciate your support and collaboration!

---

## 🙋‍♂️ About Me

**Muhammad Farrukh Umair**  
Software Engineer | AI & Data Enthusiast

📫 **Email**: [haris.umair2002@gmail.com](mailto:haris.umair2002@gmail.com)  
🔗 **LinkedIn**: [linkedin.com/in/muhammad-farrukh-umair](https://www.linkedin.com/in/muhammad-farrukh-umair/)

---

## 🧾 License

This project is open-source and available under the [MIT License](LICENSE).
