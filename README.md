# 🧠 Deep Learning-based Anomaly Detection in Gastrointestinal Images

## 📌 Overview

This project focuses on detecting abnormalities in gastrointestinal (GI) endoscopy images using deep learning. The system classifies images into **Normal** and **Abnormal** categories using a fine-tuned **ResNet50 model**.

The goal is to assist in early detection of diseases such as:

* Polyps
* Ulcerative colitis
* Esophagitis
* Barrett’s esophagus

---

## 🚀 Key Features

* ✅ Uses **ResNet50 (pretrained on ImageNet)**
* ✅ Handles **class imbalance using Weighted Sampling**
* ✅ Applies **data augmentation** for robustness
* ✅ Achieves **>93% accuracy** on test data
* ✅ Includes **ROC Curve, Confusion Matrix, and performance metrics**

---

## 📊 Dataset

* **Dataset:** HyperKvasir (Kaggle version)
* Contains labeled gastrointestinal endoscopy images

### Classes:

* **Normal (0):** anatomical landmarks
* **Abnormal (1):** pathological findings

### Data Split:

* Training: 70%
* Validation: 15%
* Testing: 15%

---

## ⚙️ Methodology

### 1️⃣ Data Preprocessing

* Resize images to **224×224**
* Normalize using ImageNet statistics
* Apply augmentations:

  * Horizontal & vertical flip
  * Rotation
  * Color jitter
  * Random affine transformations

---

### 2️⃣ Model Architecture

* Backbone: **ResNet50**
* Fine-tuning:

  * Freeze early layers
  * Train deeper layers (layer3, layer4)
* Custom classifier:

  * Fully connected layers
  * Dropout for regularization

---

### 3️⃣ Training Strategy

* Loss Function: **Weighted CrossEntropyLoss**
* Optimizer: **AdamW**
* Learning Rate Scheduler: **Cosine Annealing**
* Gradient clipping applied

---

### 4️⃣ Handling Class Imbalance

* Used **WeightedRandomSampler**
* Ensures balanced learning between normal and abnormal classes

---

## 📈 Results

### 🔥 Final Test Performance:

* **Accuracy:** 93.87%
* **Precision:** 91.75%
* **Recall:** 92.68%
* **F1-Score:** 92.21%
* **ROC-AUC:** 0.9856

### 📊 Confusion Matrix:

* TN: 583
* FP: 33
* FN: 29
* TP: 367

🎉 **Target achieved: >90% accuracy**

---

## 📉 Visualizations

The project includes:

* Accuracy & Loss curves
* Confusion Matrix
* ROC Curve

Saved at:

```
/kaggle/working/results.png
```

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
├── results.png
└── README.md
```

---

## ▶️ How to Run

1. Clone repository:

```
git clone <your-repo-link>
```

2. Install dependencies:

```
pip install -r requirements.txt
```

3. Run training:

```
python train.py
```

---

## 💡 Future Improvements

* Use **Vision Transformers (ViT)**
* Implement **attention mechanisms**
* Explore **unsupervised anomaly detection**
* Deploy as a **web-based medical tool**

---

## 🎯 Conclusion

This project demonstrates that deep learning models like ResNet50 can effectively detect abnormalities in gastrointestinal images with high accuracy, making it a promising tool for medical diagnostics.

---

## 👨‍💻 Author

**Rishikesh Gopal**
Computer Science Engineering
IIIT Vadodara International Campus Diu

---

## ⭐ If you like this project

Give it a ⭐ on GitHub!
