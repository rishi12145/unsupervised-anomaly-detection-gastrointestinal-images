# 🧠 Unsupervised Anomaly Detection in Gastrointestinal Images

### Using Multi-Level Feature Reconstruction

---

##Presentation Video

Phase 1: https://drive.google.com/file/d/10R2M-Q26WG1Iv_hKWaeoF6SfZdsAgZnv/view?usp=sharing


Phase 2: https://drive.google.com/file/d/1aTWFmZ0cQ7fUgnUafoYXk_-PsmhP_KUI/view?usp=sharing

## 📌 Overview

This project focuses on **unsupervised anomaly detection** in gastrointestinal (GI) endoscopy images using deep learning.

Unlike traditional classification approaches, the model is trained **only on normal images** and identifies abnormalities based on **reconstruction error in feature space**.

The system leverages a **ResNet50-based encoder** along with a **feature reconstruction decoder** to effectively detect and localize anomalies.

---

## 🚀 Key Features

* Unsupervised learning (trained only on normal data)
* ResNet50-based deep feature extraction
* Multi-level feature reconstruction (Layer 2, 3, 4)
* Combined loss (**MSE + SSIM**) for better reconstruction
* ROC-based threshold selection
* Heatmap-based anomaly localization

---

## 📊 Dataset

### 🔹 Source

* **HyperKvasir Dataset**
* https://www.kaggle.com/datasets/kelkalot/the-hyper-kvasir-dataset

### 🔹 Classes

* **Normal** → Anatomical landmarks
* **Abnormal** → Pathological findings

### 🔹 Abnormal Categories

* Polyps
* Esophagitis
* Ulcerative colitis
* Barrett’s esophagus

---

## 🔄 Pipeline

```text
Input Image
     ↓
Preprocessing (Resize + Normalize)
     ↓
ResNet50 Encoder (Feature Extraction)
     ↓
Multi-Level Features (Layer 2, 3, 4)
     ↓
Bottleneck Layer (Feature Refinement)
     ↓
Decoder (ConvTranspose Layers)
     ↓
Reconstructed Features
     ↓
Reconstruction Error
     ↓
Anomaly Score
     ↓
Threshold (ROC-based)
     ↓
Classification (Normal / Abnormal)
     ↓
Heatmap (Localization)
```

---

## ⚙️ Methodology

### 🔹 Data Preprocessing

* Resize images to **224×224**
* Normalize using ImageNet statistics
* Use DataLoader for efficient batching

---

### 🔹 Feature Extraction

* Backbone: **ResNet50 (pretrained)**
* Early layers are frozen
* Multi-level features extracted:

  * Layer 2 → low-level features (edges, textures)
  * Layer 3 → mid-level features (structures)
  * Layer 4 → high-level features (semantic information)

---

### 🔹 Bottleneck Layer

* Refines extracted features
* Improves representation quality

---

### 🔹 Decoder

* Uses **ConvTranspose layers**
* Reconstructs feature maps

---

### 🔹 Loss Function

* **MSE** → pixel-level similarity
* **SSIM** → structural similarity
* Combined loss improves reconstruction quality

---

## 📈 Results

### 🔥 Final Performance

* **Train Accuracy:** 99.80%
* **Validation Accuracy:** 95.45%
* **Test Accuracy:** 94.6%
* **Precision:** 93.40%
* **Recall:** 92.93%
* **F1 Score:** 93.16%
* **ROC-AUC:** 0.9888

---

### 📊 Confusion Matrix

* **TN:** 590
* **FP:** 26
* **FN:** 28
* **TP:** 368

✔ High detection accuracy with low false predictions

---

### 📊 ROC Curve

* **AUROC ≈ 0.9888**
* Indicates strong separation between normal and abnormal classes

---

## 🛠️ Tech Stack

* Python
* PyTorch
* OpenCV
* NumPy
* Matplotlib & Seaborn
* Scikit-learn

---

## 📂 Project Structure

```
├── data/
├── models/
├── training/
├── evaluation/
├── heatmaps/
├── results/
└── README.md
```

---

## 💡 Future Improvements

* Add attention mechanisms
* Explore Vision Transformers (ViT)
* Improve anomaly localization
* Deploy as a web-based application

---

## 📄 Research Work

Following the project review (April 16), this work was identified to have strong research potential.

We are currently working on extending this project into a **research paper**.

---

## 👨‍💻 Author

**Rishikesh Gopal**
CSE | IIIT Vadodara – International Campus Diu

---

## ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub!
