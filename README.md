🧠 Unsupervised Anomaly Detection in Gastrointestinal Images
Using Multi-Level Feature Reconstruction
📌 Overview

This project focuses on unsupervised anomaly detection in gastrointestinal (GI) endoscopy images using deep learning.

Unlike traditional classification models, this approach learns only from normal images and identifies abnormalities based on how well the model can reconstruct image features.

The system leverages a pretrained ResNet50 encoder combined with a feature reconstruction decoder, enabling it to detect and localize anomalies such as:

Polyps
Ulcerative colitis
Esophagitis
Barrett’s esophagus
🚀 Key Features
✅ Unsupervised Learning Approach (trained only on normal data)
✅ ResNet50-based Feature Extraction
✅ Multi-Level Feature Reconstruction (Layer 2, 3, 4)
✅ Combined Loss (MSE + SSIM) for better reconstruction
✅ ROC-based Threshold Selection
✅ Grad-CAM Heatmaps for anomaly localization
✅ Achieves ~94.66% Accuracy and AUROC ≈ 0.9888
📊 Dataset
Dataset: HyperKvasir (Kaggle)
Source: https://www.kaggle.com/datasets/kelkalot/the-hyper-kvasir-dataset

The dataset consists of gastrointestinal endoscopy images categorized into:

Classes:
Normal Images: Anatomical landmarks
Abnormal Images: Pathological findings
Abnormal Categories:
Polyps
Esophagitis
Ulcerative colitis
Barrett’s esophagus
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
Reconstruction Error Calculation
     ↓
Anomaly Score
     ↓
Threshold (ROC-based)
     ↓
Classification (Normal / Abnormal)
     ↓
Heatmap (Localization of anomaly)
⚙️ Methodology
1️⃣ Data Preprocessing
Resize all images to 224 × 224
Normalize using ImageNet mean and standard deviation
Organize dataset into normal and abnormal folders
Use DataLoader for efficient batch processing
2️⃣ Feature Extraction (Encoder)
Backbone: ResNet50 (pretrained on ImageNet)
Early layers are frozen to retain learned representations
Extract multi-level features:
Layer 2 → Low-level (edges, textures)
Layer 3 → Mid-level (shapes, structures)
Layer 4 → High-level (semantic information)
3️⃣ Bottleneck Layer
Refines and compresses extracted features
Ensures meaningful representation before reconstruction
4️⃣ Decoder (Reconstruction)
Uses ConvTranspose layers for upsampling
Reconstructs features instead of raw pixels
Learns only normal feature distribution
5️⃣ Loss Function
Mean Squared Error (MSE) → Pixel similarity
Structural Similarity Index (SSIM) → Structural integrity

👉 Combined loss improves reconstruction quality significantly

6️⃣ Training Strategy
Train only on normal images
Encoder mostly frozen, decoder trained
Optimization:
Adam optimizer
Learning rate scheduler
Gradient clipping
7️⃣ Anomaly Detection
Compute reconstruction error between:
Original features
Reconstructed features
Higher error → higher anomaly probability
Generate:
Anomaly Score
Binary Classification using ROC threshold
8️⃣ Localization (Explainability)
Use Grad-CAM to generate heatmaps
Highlights regions responsible for anomaly detection
Helps in medical interpretability
📈 Results
🔥 Final Performance:
Train Accuracy: 99.80%
Validation Accuracy: 95.45%
Test Accuracy: 94.6%
Precision: 93.40%
Recall: 92.93%
F1 Score: 93.16%
ROC-AUC: 0.9888
📊 Confusion Matrix:
True Negatives (TN): 590
False Positives (FP): 26
False Negatives (FN): 28
True Positives (TP): 368
📉 Observations
Strong separation between normal and abnormal classes
Minimal overfitting observed
High AUROC indicates excellent discrimination ability
Heatmaps successfully localize pathological regions
📊 Visualizations

The project includes:

Training & Validation Accuracy Curves
Training & Validation Loss Curves
Confusion Matrix
ROC Curve
Grad-CAM Heatmaps
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
└── README.md
▶️ How to Run
git clone <your-repo-link>
cd project-folder

pip install -r requirements.txt

python train.py
💡 Future Improvements
Add Attention Mechanisms for better feature focus
Explore Vision Transformers (ViT)
Improve anomaly localization accuracy
Deploy as a real-time medical diagnostic tool
Extend to fully unsupervised / self-supervised frameworks
🎯 Conclusion

This project demonstrates that unsupervised deep learning with multi-level feature reconstruction can effectively detect anomalies in gastrointestinal images.

By learning only normal patterns, the model achieves:

High accuracy
Strong generalization
Effective anomaly localization

This approach shows strong potential for real-world medical screening applications.

📄 Research Extension

After the project review on 16th April 2026, the work was recognized to have strong research potential.

👉 We are currently working on extending this project into a research paper for publication.

👨‍💻 Author

Rishikesh Gopal
Computer Science Engineering
IIIT Vadodara – International Campus Diu

⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub!
