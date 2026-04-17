📌 Overview

This project focuses on unsupervised anomaly detection in gastrointestinal (GI) endoscopy images using deep learning.

Unlike traditional classification models, this approach learns only from normal images and detects abnormalities based on reconstruction error in feature space.

💡 The model leverages:

ResNet50 encoder
Multi-level feature extraction
Feature reconstruction decoder

🎯 Goal: Assist in early detection of diseases like:

Polyps
Ulcerative colitis
Esophagitis
Barrett’s esophagus
🚀 Key Features
🧠 Unsupervised Learning (trained only on normal data)
🔍 Multi-Level Feature Extraction (Layer 2, 3, 4)
⚙️ Combined Loss (MSE + SSIM)
📊 ROC-based Threshold Selection
🔥 Grad-CAM Heatmaps for localization
📈 High performance with AUROC ≈ 0.9888
🖼️ Model Architecture

(Add your diagram image here later)

[ Input Image ]
        ↓
[ Preprocessing ]
        ↓
[ ResNet50 Encoder ]
        ↓
[ Multi-Level Features ]
        ↓
[ Bottleneck Layer ]
        ↓
[ Decoder ]
        ↓
[ Reconstruction ]
        ↓
[ Error Calculation ]
        ↓
[ Anomaly Score ]
        ↓
[ Classification ]
        ↓
[ Heatmap Output ]
🔄 Complete Pipeline
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
📊 Dataset

📂 HyperKvasir Dataset
🔗 https://www.kaggle.com/datasets/kelkalot/the-hyper-kvasir-dataset

Classes:
Normal (0): Anatomical landmarks
Abnormal (1): Pathological findings
Abnormal Categories:
Polyps
Esophagitis
Ulcerative colitis
Barrett’s esophagus
⚙️ Methodology
1️⃣ Data Preprocessing
Resize → 224×224
Normalize → ImageNet stats
DataLoader → Efficient batching
2️⃣ Feature Extraction
Backbone: ResNet50 (pretrained)
Freeze early layers
Extract:
Layer 2 → Low-level features
Layer 3 → Mid-level features
Layer 4 → High-level features
3️⃣ Bottleneck Layer
Refines extracted features
Improves reconstruction quality
4️⃣ Decoder
ConvTranspose layers
Reconstructs feature maps
5️⃣ Loss Function
MSE → pixel similarity
SSIM → structural similarity
6️⃣ Anomaly Detection
Compute reconstruction error
Generate anomaly score
Apply ROC threshold
7️⃣ Explainability
Grad-CAM heatmaps
Highlights abnormal regions
📈 Results
🔥 Final Performance:
Train Accuracy: 99.80%
Validation Accuracy: 95.45%
Test Accuracy: 94.6%
Precision: 93.40%
Recall: 92.93%
F1 Score: 93.16%
ROC-AUC: 0.9888
📊 Visual Results

(Add your plots here — VERY IMPORTANT for premium look)

📉 Accuracy & Loss Curves

🔍 Confusion Matrix & ROC Curve

(Included in results.png)

🔥 Grad-CAM Visualization

(Add heatmap image here later)

🛠️ Tech Stack
Python
PyTorch
OpenCV
NumPy
Matplotlib & Seaborn
Scikit-learn
📂 Project Structure
├── data/
├── models/
├── training/
├── evaluation/
├── heatmaps/
├── results/
├── notebook.ipynb
└── README.md
▶️ How to Run
git clone https://github.com/your-username/your-repo.git
cd your-repo

pip install -r requirements.txt

python train.py
💡 Future Improvements
Add Attention Mechanisms
Explore Vision Transformers (ViT)
Improve localization accuracy
Deploy as web-based diagnostic tool
📄 Research Work

📌 After the project review on 16th April, this work was recognized for its strong research potential.

👉 Currently, we are working on converting this project into a research paper for publication.

👨‍💻 Author

Rishikesh Gopal
CSE | IIIT Vadodara – Diu

⭐ Support

If you like this project, give it a ⭐ on GitHub!
