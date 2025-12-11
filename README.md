# From Text to Sign: Deep Learning-Based Hand Gesture Generation

This project converts text into sign language gesture images using computer vision and machine learning techniques. The work was developed and tested entirely on **Google Colab**, and the notebook contains the full implementation—preprocessing, feature extraction, model training, and UI generation.

The goal of the project is to support communication accessibility by automatically generating sign gestures for each alphabet entered by the user.

---

## 📌 1. Project Overview

The system takes text as input and converts each character into its corresponding sign-language gesture.  
The pipeline includes:

- Image preprocessing (contrast enhancement, resizing, denoising)
- Hand region extraction using contours
- Landmark extraction using MediaPipe
- Gesture classification using ML models
- Generating gesture sequences as animations
- A simple UI frontend built in Gradio

All training, testing, and results were generated on **Google Colab**.

---

## 🧠 2. System Workflow

**Text Input → Preprocessing → Feature Extraction → Classification → Animation → Output Preview**

Main components:

- **CLAHE** for contrast enhancement  
- **Super-resolution** for improving low-quality gesture images  
- **Canny edge detection** + contouring for hand segmentation  
- **MediaPipe Hands** for extracting 21 keypoints  
- **Random Forest** and **SVM** for gesture classification  
- **Gradio** for an interactive interface  

---

## ⚙️ 3. Methodology

### **Step 1 — Preprocessing**
- Resize image to 256×256  
- Convert to grayscale  
- Apply CLAHE  
- Enhance with super-resolution  
- Extract contours for Region of Interest  

### **Step 2 — Feature Extraction**
- MediaPipe Hands returns **21 (x, y, z)** coordinates  
- Features are normalized and fed into ML models  

### **Step 3 — Classification**
Two models were tested:
- Random Forest  
- SVM  

Used for classifying 24 ASL alphabet gestures (except dynamic gestures J & Z).

### **Step 4 — Text-to-Sign Animation**
- Each character maps to its gesture  
- Frames stitched into an animation/GIF  
- Shown in UI  
- User can download the generated animation  

---

## 🧪 4. Evaluation

Since the project is more visual in nature, evaluation focused on:

- Accuracy of gesture classification  
- Clarity of enhanced images  
- Smoothness of gesture animation  
- Correctness of letter-to-gesture mapping  

All observations were tested inside Colab using the preprocessed dataset.

---

## 📊 5. Outputs

The system generates:

- Enhanced gesture images  
- Extracted keypoint plots  
- Predicted gesture classes  
- A full gesture sequence animation  

You can include sample screenshots in the `assets/` folder.

---

## 💻 6. Running the Project (Colab Version)

### **1. Install Dependencies**
```bash
pip install mediapipe opencv-python numpy pandas scikit-learn gradio
```

### **2. Upload the notebook to Colab**
Open:
```
text_to_sign_gesture_generation_.ipynb
```

### **3. Run all cells**
Colab will:
- Preprocess dataset  
- Extract features  
- Train models  
- Generate UI  

### **4. Launch UI**
The last cell will open a Gradio interface.

Enter text → get sign gesture image sequence.

---

## 📁 7. Suggested Project Structure

```
From-Text-to-Sign-Gestures-using-Media-pipe/
│
├── notebooks/
│   ├── Feature_Extraction.ipynb
│   └── text_to_sign_gesture_generation_.ipynb
│
├── assets/
│   └── hello_animation.mp4
│
├── docs/
│   └── From_Text_to_Sign_thesis.docx
│
└── README.md

```


## 🎯 8. Summary

This project demonstrates an end-to-end workflow for converting text into sign language gestures using a mix of preprocessing, handcrafted features, ML models, and UI design.  
Running on Colab made the experimentation process simple and reproducible.

---


