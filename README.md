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

<img width="450" height="360" alt="Image" src="https://github.com/user-attachments/assets/6ba7e524-437f-43cf-86f8-459a1f86895c" />
<img width="450" height="360" alt="Image" src="https://github.com/user-attachments/assets/9a3f2df9-c359-4c3b-aaad-8dc15cb115ff" />
<img width="450" height="360" alt="Image" src="https://github.com/user-attachments/assets/2e17a99e-89e3-4112-89a1-824752ce2bc2" />

---

## Data

Data for training from [kaggle](https://www.kaggle.com/) and [pinterest](https://id.pinterest.com/)
