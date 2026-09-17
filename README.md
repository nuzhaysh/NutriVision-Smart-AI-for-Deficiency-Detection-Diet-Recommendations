# 🥗 NutriVision – Smart AI for Deficiency Detection & Diet Recommendations

A deep learning framework that screens for nutritional deficiencies from eye and nail images — non-invasively, in real time — and delivers personalized dietary recommendations through an integrated conversational AI.

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?logo=keras&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?logo=django&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white)
![License](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey)

📄 **Published research:** *[NutriVision: A Deep Learning-Based Framework for Nutritional Deficiency Detection and Dietary Recommendation using Eye and Nail Images](https://www.ijert.org/nutrivision-a-deep-learning-based-framework-for-nutritional-deficiency-detection-and-dietary-recommendation-using-eye-and-nail-images-ijertv15is040363)** — IJERT, Vol. 15, Issue 04, April 2026 · DOI: [10.5281/zenodo.19552927](https://doi.org/10.5281/zenodo.19552927)

---

## 📋 Overview

Conventional nutritional deficiency screening relies on invasive, lab-based blood tests — impractical for large-scale or frequent checks, especially in resource-limited settings. NutriVision offers a non-invasive alternative: it analyzes visual biomarkers in the conjunctiva (eye) and nail bed — regions long associated with underlying nutritional conditions — and classifies deficiency type using transfer learning, then maps predictions to actionable dietary guidance.

> ⚠️ NutriVision is designed as a **preliminary screening and decision-support tool**, not a replacement for professional medical diagnosis.

## ✨ Key Features

- **Dual-modality detection** — separate models for eye and nail image analysis
- **Transfer learning with InceptionV3** — multi-scale convolutional feature extraction tuned for subtle color/texture variations
- **Rule-based dietary recommendation engine** — maps each predicted deficiency to relevant food sources
- **Conversational AI assistant** — generates personalized, context-aware guidance based on predictions and user profile (dietary preferences, allergies)
- **Web-based real-time inference** — built on Django with a MySQL backend

## 🧠 Model & Methodology

| | |
|---|---|
| **Base architecture** | InceptionV3 (pre-trained on ImageNet, transfer learning) |
| **Fine-tuning** | Last 50 layers unfrozen |
| **Head** | Global Average Pooling → Dense (1024, ReLU) → Dropout (0.5) → Softmax |
| **Optimizer** | Adam (lr = 1e-4) |
| **Loss** | Categorical cross-entropy |
| **Batch size** | 32 |
| **Regularization** | Dropout, early stopping (val loss), LR reduction on plateau |
| **Augmentation** | Rotation (±30°), width/height shift (±20%), zoom (±20%), horizontal flip, brightness jitter (0.8–1.2×) |
| **Baselines compared** | Sequential CNN, MobileNet (InceptionV3 outperformed both) |

InceptionV3 was chosen over lighter alternatives because its parallel multi-scale filters (1×1, 3×3, 5×5) capture both fine-grained texture and broader color/contextual patterns — critical for distinguishing subtle deficiency indicators.

## 🗂️ Dataset

Sourced from publicly available Kaggle datasets — **7,325 images total** (4,877 eye + 2,448 nail), filtered down to clinically relevant, non-occluded samples.

**Eye dataset** — 602 valid diagnostic samples across 5 classes:

| Class | Images |
|---|---|
| Normal | 126 |
| Vitamin A Deficiency | 117 |
| Vitamin B Complex Deficiency | 120 |
| Vitamin B12 Deficiency | 119 |
| Vitamin B3 Deficiency | 120 |

**Nail dataset** — 1,970 valid diagnostic samples across 8 classes:

| Class | Images |
|---|---|
| Healthy | 248 |
| Iron Deficiency | 250 |
| Protein Deficiency | 264 |
| Vitamin B12 Deficiency | 300 |
| Vitamin B7 Deficiency | 276 |
| Vitamin C Deficiency | 300 |
| Vitamin D Deficiency | 282 |
| Zinc Deficiency | 50 |

(Images with occlusions — eyewear, closed eyes, nail polish — were excluded during preprocessing.)

## 📊 Results

| Model | Validation Accuracy |
|---|---|
| **Nail-based model** | **97–98%** |
| Eye-based model | 95–96% |

The nail-based model consistently outperformed the eye-based model — nail images carry both color *and* structural cues (ridging, discoloration), while eye-based detection relies solely on subtle color variation, which is more sensitive to lighting and shows higher inter-class similarity.

## 🚀 System Architecture

```
Input Image (eye/nail)
        │
        ▼
Preprocessing & Augmentation (resize 224×224, normalize, augment)
        │
        ▼
InceptionV3 Feature Extraction (transfer learning)
        │
        ▼
Deficiency Classification (softmax)
        │
        ▼
Rule-Based Dietary Recommendation Engine
        │
        ▼
Conversational AI → Personalized Guidance
```

Deployed as a web application (Django backend + MySQL database) supporting real-time image upload, inference, and recommendation delivery.

## ⚠️ Limitations

- Class imbalance across categories (e.g., Zinc Deficiency has only 50 samples vs. 300 for others)
- Eye-based detection is sensitive to illumination and shows overlapping features between visually similar classes
- No dedicated held-out test set — validation performance used as a generalization proxy
- Dietary recommendations are rule-based (deterministic mapping), not adaptive/learned
- Labels reflect visually distinguishable categories, not clinically confirmed diagnoses

## 🔮 Future Work

- [ ] Expand dataset size and diversity; incorporate clinically validated labels
- [ ] Improve eye-based feature separability to reduce classification ambiguity
- [ ] Add adaptive learning to the recommendation module based on user feedback
- [ ] Explore additional non-invasive indicators (skin, facial features)
- [ ] Conduct real-world user studies and large-scale deployment testing

## 📚 Citation

If you reference this work, please cite:

```
Aysha Nuzha Nazeer, Angelin Maria Jose, Najiya Fathima K T, Nithya K Unni, Sona P. (2026).
NutriVision: A Deep Learning-Based Framework for Nutritional Deficiency Detection and
Dietary Recommendation using Eye and Nail Images. International Journal of Engineering
Research & Technology (IJERT), Volume 15, Issue 04. DOI: 10.5281/zenodo.19552927
```

## 🙏 Acknowledgments

Developed at the Department of Computer Science and Engineering, Vimal Jyothi Engineering College (APJ Abdul Kalam Technological University), under the supervision of Ms. Sona P.


<!-- 💡 Add setup/installation instructions here once your repo structure is finalized -->
