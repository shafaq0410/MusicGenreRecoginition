# 🎵 Classify: Real-Time Music Genre Recognition System

## 📘 Executive Summary
**Classify** is a full-stack web application designed for **real-time music genre classification**.  
It integrates a simple and responsive frontend (HTML, CSS, JavaScript) with a robust backend (Python Flask).  
At its core lies a trained **2D Convolutional Neural Network (CNN)** model capable of predicting the genre of an uploaded audio file.  

The model was trained on the **GTZAN dataset**, enabling classification across **ten musical genres**.  
Users can upload songs, view instant predictions with confidence scores, and interact with an intuitive interface.  

---

## 🎯 Introduction

### 🧩 Problem Statement
The rapid growth of digital music libraries has made manual genre labeling inefficient and time-consuming.  
Accurate genre classification is crucial for recommendation systems, playlist organization, and music retrieval.  
**Classify** automates this process, providing a reliable and fast genre prediction tool.

### 🚀 Project Objectives
- **Develop a Deep Learning Model:**  
  Train a CNN to classify songs into 10 genres using extracted spectrograms.  
- **Implement a Flask Interface:**  
  Build a simple file upload web app for predictions.  
- **Ensure Ease of Use:**  
  Keep the UI lightweight and focused on functionality.  
- **Maintain Scalability:**  
  Make the system modular for future integration or deployment.

### 📏 Scope and Limitations
- **Genres:** Blues, Classical, Country, Disco, Hip-Hop, Jazz, Metal, Pop, Reggae, Rock.  
- **Input Format:** `.mp3`, `.wav` audio files.  
- **Model File:** Uses a pre-trained CNN model (`cnn.h5`).  
- **Limitations:** No real-time streaming or multi-file batch uploads yet.

---

## 🧠 System Design and Implementation

### 🧩 1. Machine Learning Model
#### Dataset: **GTZAN Genre Collection**
- **Tracks:** 1,000 (30 sec each)
- **Genres:** 10 (100 per genre)
- **Format:** `.wav`

#### 🎼 Data Preprocessing
1. Load and resample the audio.
2. Apply **Short-Time Fourier Transform (STFT)**.
3. Convert to **Mel Spectrogram**.
4. Scale to decibels for CNN input.

#### 🧱 Model Architecture
1. Input (128×128×1)  
2. Conv2D Layers (32–128 filters)  
3. ReLU Activation + MaxPooling  
4. Flatten + Dense Layers  
5. Output Layer → Softmax (10 genres)

#### ⚙️ Training Configuration
| Parameter | Value |
|------------|--------|
| Optimizer | Adam |
| Loss Function | Categorical Crossentropy |
| Epochs | 150 |
| Batch Size | 128 |
| Test Accuracy | **82%** |

Alternate trial (30 epochs, batch size 64): **65% accuracy**

---

### 🌐 2. Frontend and User Flow
1. **Homepage:** File upload interface.  
2. **Upload:** Flask receives file → processes through CNN model.  
3. **Prediction:** Displays genre + confidence score.  
4. **Error Handling:** Invalid files prompt clear feedback.  

The UI focuses on simplicity and quick interaction.

---

## 🧩 3. Comparison of Models
| Model | Accuracy |
|--------|-----------|
| Decision Tree | 0.5160 |
| Random Forest | 0.7009 |
| ElasticNet | 0.7063 |
| Logistic Regression | 0.7624 |
| SVM (RBF) | 0.7610 |
| **CNN 2D** | **0.8200** |

---

## ⚙️ Getting Started

### 🧾 Prerequisites
Ensure the following tools are installed:
- Python ≥ 3.12  
- pip  
- Virtual environment (`venv`)  
- Web browser  

### 🧭 Setup Instructions

# Clone the repository
git clone https://github.com/shafaq0410/MusicGenreRecoginition.git
cd MusicGenreRecoginition

# Create virtual environment
python -m venv venv_songs

# Activate it
venv_songs\Scripts\activate    # (Windows)

# Install dependencies
pip install -r requirements.txt

# Run the Flask app
python app.py
