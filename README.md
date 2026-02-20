# Botnet Detection using Deep Learning (LSTM & FCNN)

Deep learning–based botnet detection project using **LSTM networks and Fully Connected Neural Networks (FCNN)** trained on the **CTU-13 cybersecurity dataset**.
This repository demonstrates how temporal modeling and imbalance-aware learning improve malicious traffic detection in real-world network environments.

---

## 📌 Project Overview

Botnets are networks of compromised devices capable of launching coordinated cyberattacks such as DDoS, spam campaigns, and data exfiltration. Traditional signature-based systems often fail to detect evolving threats.

This project applies deep learning techniques to automatically learn behavioral patterns from network traffic flows and classify traffic as **normal** or **botnet activity**.

Key focus areas:

* Temporal sequence modeling using LSTM
* Imbalanced data learning
* Network traffic feature engineering
* Deep learning evaluation for cybersecurity tasks

---

## 🧠 Models Implemented

### Bidirectional LSTM with Attention

* Learns forward & backward temporal dependencies
* Attention mechanism emphasizes important sequence information

### Stacked LSTM ⭐ (Best Performing)

* Multi-layer sequential learning
* Batch normalization + dropout regularization
* Optimized for imbalanced classification

### Fully Connected Neural Network (FCNN)

* Learns high-dimensional feature interactions
* Serves as baseline comparison model

---

## ⚙️ Methodology

### Data Preprocessing

* Missing value handling
* Invalid network flow removal
* IQR-based outlier clipping
* Feature normalization using RobustScaler
* Label binarization & deduplication

### Feature Engineering

* Temporal features (hour, weekday, weekend)
* Network metrics:

  * Bytes per packet
  * Packets per second
  * Bytes per second
  * Source byte ratio
* Mean encoding for categorical attributes

### Imbalance Handling

* SMOTE
* SMOTETomek
* Focal Loss

### Training Strategy

* 5-Fold Stratified Cross Validation
* Early Stopping
* Learning rate scheduling
* Adam optimizer

---

## 📊 Dataset

**CTU-13 Dataset**

* Real-world labeled network traffic
* ~1.6M flow records
* Highly imbalanced botnet vs normal traffic

---

## 📈 Results

| Model               | PR AUC    | Precision | Recall   | F1-score |
| ------------------- | --------- | --------- | -------- | -------- |
| Bi-LSTM + Attention | 0.783     | 0.43      | 0.91     | 0.59     |
| **Stacked LSTM**    | **0.833** | **0.50**  | **0.92** | **0.64** |
| FCNN + SMOTETomek   | 0.799     | 0.47      | 0.91     | 0.62     |
| FCNN + SMOTE        | 0.806     | 0.46      | 0.91     | 0.61     |

Stacked LSTM achieved the strongest performance for detecting minority botnet traffic.

---

## 📂 Repository Structure

```
botnet-detection-deep-learning/
│
├── data/                # CTU-13 dataset samples & processed flows
├── figures/             # Visualizations (PR curves, plots, analysis figures)
├── models/              # Saved trained deep learning models
├── notebooks/           # Jupyter notebooks for experiments & training
│
├── scaler.npy           # Saved feature scaler
├── selected_features.npy # Selected feature indices
│
├── botnet-detection-deep-learning-ctu13.pdf
│                         # Full technical research report
└── README.md
```

---

## 🛠 Tech Stack

* Python
* TensorFlow / Keras
* Scikit-learn
* Pandas & NumPy
* Matplotlib

---

## 📄 Research Report

Full technical documentation:

👉 **botnet-detection-deep-learning-ctu13.pdf**

---

## 🚀 Key Contributions

* Developed deep learning pipeline for cybersecurity anomaly detection
* Engineered temporal & statistical network traffic features
* Applied imbalance-aware learning techniques
* Demonstrated effectiveness of stacked LSTM architectures

---

## 👨‍💻 Author

**Ahmad Zaki**
Informatics Engineering — Universitas Brawijaya

GitHub: https://github.com/ahmdzzzki

---

## 🔮 Future Improvements

* Real-time detection pipeline
* CNN–LSTM hybrid models
* Explainable AI (SHAP / LIME)
* Evaluation on larger intrusion datasets

---

⭐ If you find this project useful, consider starring the repository!
