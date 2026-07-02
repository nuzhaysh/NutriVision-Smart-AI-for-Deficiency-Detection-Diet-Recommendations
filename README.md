# 🥗 NutriVision – Smart AI for Deficiency Detection & Diet Recommendations

NutriVision is an AI-powered web application designed for the **non-invasive detection of nutritional deficiencies** using **eye and nail images**. The system leverages **Deep Learning (InceptionV3)** and computer vision techniques to analyze visual biomarkers associated with nutritional deficiencies such as **Iron, Vitamin B12, Vitamin A, Vitamin D, Protein, Vitamin C, Vitamin B7, Zinc**, and more. After prediction, the application provides **personalized diet recommendations** and an **AI-powered nutrition chatbot** to help users understand their condition and improve their nutritional health. :contentReference[oaicite:0]{index=0}

---

## 📌 Overview

Nutritional deficiencies often remain undiagnosed until noticeable symptoms appear. Traditional diagnosis typically requires laboratory tests, which can be expensive, invasive, and inaccessible in many regions. NutriVision aims to provide an intelligent, accessible, and cost-effective preliminary screening solution by analyzing eye and nail images using deep learning.

The application integrates image preprocessing, deep learning-based classification, personalized dietary recommendations, user health profiles, prediction history, and an AI nutrition assistant into a single web platform. It is intended as a **screening and decision-support tool** rather than a replacement for professional medical diagnosis. :contentReference[oaicite:1]{index=1} :contentReference[oaicite:2]{index=2}

---

## ✨ Features

- 🔍 Nutritional deficiency detection using Eye Images
- 💅 Nutritional deficiency detection using Nail Images
- 🧠 Deep Learning model based on InceptionV3
- 🖼️ Image preprocessing and augmentation
- 📊 Prediction confidence score
- 🥗 Personalized diet and lifestyle recommendations
- 🤖 AI-powered Nutrition Chatbot
- 👤 User registration and profile management
- 📁 Prediction history tracking
- 💬 Health tips management
- 🌐 Responsive Django web application

---

## 🏗️ System Workflow

1. User registers and logs into the application.
2. Uploads an eye or nail image.
3. Image undergoes preprocessing (resize, normalization, augmentation).
4. The trained InceptionV3 model predicts the nutritional deficiency.
5. The prediction confidence is displayed.
6. Personalized dietary recommendations are generated.
7. Users can interact with the AI chatbot for nutrition-related guidance.
8. Prediction history is stored for future reference. :contentReference[oaicite:3]{index=3}

---

## 🧠 Deep Learning Model

The project uses **Transfer Learning** with **InceptionV3**, pretrained on ImageNet. The final classification layers are customized and fine-tuned for nutritional deficiency detection.

### Image Processing
- Image resizing (224 × 224)
- Pixel normalization
- Data augmentation
- Rotation
- Horizontal flipping
- Zooming
- Brightness adjustment

These preprocessing techniques improve model robustness and generalization under varying image conditions. :contentReference[oaicite:4]{index=4} :contentReference[oaicite:5]{index=5}

---

## 🛠️ Tech Stack

### Backend
- Python
- Django

### AI & Machine Learning
- TensorFlow
- Keras
- InceptionV3
- OpenCV
- NumPy

### Database
- MySQL

### Frontend
- HTML
- CSS
- Bootstrap
- JavaScript

### Other Libraries
- Pillow
- Matplotlib
- Google Gemini API (Nutrition Chatbot)

---

## 📂 Project Modules

- User Authentication
- User Profile Management
- Eye Deficiency Prediction
- Nail Deficiency Prediction
- AI Nutrition Chatbot
- Health Tips Module
- Feedback Management
- Prediction History
- Admin Dashboard

The Django application exposes dedicated routes for authentication, predictions, chatbot interaction, health tips, profile management, and prediction history. :contentReference[oaicite:6]{index=6}

---

## 📊 Model Performance

The trained models achieved high validation performance:

| Model | Validation Accuracy |
|--------|--------------------|
| Nail Image Model | **95–98%** |
| Eye Image Model | **95–97%** |

The nail-based model achieved slightly better performance because nail images provide stronger structural and texture features than eye images. :contentReference[oaicite:7]{index=7} :contentReference[oaicite:8]{index=8}

---

## 💬 AI Nutrition Chatbot

The integrated chatbot helps users by:

- Explaining prediction results
- Answering nutrition-related questions
- Providing personalized dietary advice
- Considering user health conditions and dietary preferences
- Suggesting healthy lifestyle improvements

The chatbot combines stored knowledge with generative AI responses to deliver personalized nutrition guidance. :contentReference[oaicite:9]{index=9}

---

## 📸 Supported Predictions

### Eye Analysis
- Healthy
- Vitamin A Deficiency
- Vitamin B Complex Deficiency
- Vitamin B12 Deficiency
- Vitamin B3 Deficiency

### Nail Analysis
- Healthy
- Iron Deficiency
- Protein Deficiency
- Vitamin B12 Deficiency
- Vitamin B7 Deficiency
- Vitamin C Deficiency
- Vitamin D Deficiency
- Zinc Deficiency :contentReference[oaicite:10]{index=10}

---

## 🚀 Future Enhancements

- Mobile application
- Real-time camera prediction
- Explainable AI (Grad-CAM)
- Clinical dataset integration
- Multi-modal diagnosis
- Cloud deployment
- Doctor consultation module
- Wearable device integration

Future work also includes improving dataset diversity, adaptive recommendations, and integrating additional visual biomarkers for more comprehensive screening. :contentReference[oaicite:11]{index=11}

---

## ⚠️ Disclaimer

**NutriVision is intended for educational purposes and preliminary nutritional screening only. It is not a substitute for professional medical diagnosis or laboratory testing. Users should consult qualified healthcare professionals for accurate diagnosis and treatment.**

---

## 👨‍💻 Developed Using

- Python
- Django
- TensorFlow
- Keras
- OpenCV
- MySQL
- HTML
- CSS
- Bootstrap
- JavaScript

---

⭐ If you found this project useful, don't forget to **Star** the repository!
