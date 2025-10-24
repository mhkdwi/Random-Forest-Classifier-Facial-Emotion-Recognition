# 🎭 Facial Emotion Recognition using Face Landmarks

This project detects human facial emotions in real time using **MediaPipe Face Mesh** and **Random Forest Classifier**.  
By analyzing the geometric structure of the face through 3D landmarks, the system recognizes basic facial expressions such as **Happy**, **Sad**, and **Surprised**.  

It provides a lightweight yet effective approach for facial emotion recognition without the need for deep learning models, making it fast and efficient for live video processing.

---

## 🧩 Program Workflow

### 1. Data Preparation (`prepare_data.py`)
- Reads facial images from the `data/` directory, each subfolder representing an emotion.  
- Extracts **468 face landmarks × 3 coordinates (x, y, z)** using MediaPipe.  
- Saves the landmark features and emotion labels into `data.txt`.

### 2. Model Training (`train_model.py`)
- Loads `data.txt` and splits it into training and testing sets.  
- Trains a **Random Forest Classifier** to learn the relationship between facial landmarks and emotion categories.  
- Prints out accuracy and confusion matrix for evaluation.  
- Saves the trained model to `model` using pickle.

### 3. Real-Time Prediction (`test_model.py`)
- Opens webcam using OpenCV and captures each frame.  
- Extracts face landmarks in real time using MediaPipe.  
- Predicts the emotion class with the trained Random Forest model.  
- Displays the predicted emotion label (e.g., “HAPPY”) directly on the webcam feed.

---

## 🖼️ Example Output

<img width="150" height="120" alt="Image" src="https://github.com/user-attachments/assets/6d1bcf59-6557-42b2-87f3-cdf6162b8c17" />

---

## Data

Data for train from [kaggle](https://www.kaggle.com/) and [pinterest](https://id.pinterest.com/)
