# Botnet Detection using Deep Learning (LSTM & FCNN)

Deep learning–based botnet detection system using advanced preprocessing and sequence modeling techniques on the **CTU-13 cybersecurity dataset**.
This project explores how temporal neural networks can identify malicious network traffic under highly imbalanced data conditions.

---

## 📌 Overview

Botnets remain one of the most critical cybersecurity threats, enabling large-scale attacks such as Distributed Denial of Service (DDoS), data exfiltration, and automated intrusion campaigns. Traditional detection systems struggle to identify evolving attack patterns due to their reliance on static signatures.

This project applies **deep learning approaches** to detect botnet activity from real-world network traffic by learning temporal and statistical patterns directly from data.

The study evaluates multiple neural architectures and demonstrates the effectiveness of **Stacked LSTM models** for detecting minority attack classes in imbalanced datasets.

---

## 🎯 Objectives

* Detect botnet traffic from network flow data
* Handle severe class imbalance in cybersecurity datasets
* Compare sequential and fully connected neural architectures
* Improve detection robustness using advanced preprocessing and optimization techniques

---

## 🧠 Models Implemented

### 1. Bidirectional LSTM with Attention

* Captures forward and backward temporal dependencies
* Attention mechanism highlights important sequence features

### 2. Stacked LSTM (Best Performing Model)

* Multi-layer temporal representation learning
* Batch normalization and progressive dropout
* Optimized for imbalanced classification

### 3. Fully Connected Neural Network (FCNN)

* Learns high-dimensional feature interactions
* Serves as non-sequential baseline comparison

---

## ⚙️ Methodology

### Data Preprocessing

* Missing value handling
* Invalid flow removal
* Outlier management using IQR clipping
* Feature normalization (RobustScaler)
* Label binarization and deduplication

### Feature Engineering

* Temporal features (hour, weekday, weekend)
* Network metrics:

  * Bytes per packet
  * Packets per second
  * Bytes per second
  * Source byte ratio
* Mean encoding for categorical variables

### Imbalance Handling

* SMOTE
* SMOTETomek
* Focal Loss

### Training Strategy

* 5-Fold Stratified Cross Validation
* Early Stopping
* ReduceLROnPlateau
* Adam Optimizer with learning rate scheduling

---

## 📊 Dataset

**CTU-13 Dataset**
A real-world labeled network traffic dataset containing normal and botnet communication flows.

* ~1.6M network records
* Highly imbalanced classes
* Flow-based network features

---

## 📈 Results

| Model               | PR AUC    | Precision | Recall   | F1-score |
| ------------------- | --------- | --------- | -------- | -------- |
| Bi-LSTM + Attention | 0.783     | 0.43      | 0.91     | 0.59     |
| **Stacked LSTM**    | **0.833** | **0.50**  | **0.92** | **0.64** |
| FCNN + SMOTETomek   | 0.799     | 0.47      | 0.91     | 0.62     |
| FCNN + SMOTE        | 0.806     | 0.46      | 0.91     | 0.61     |

✅ Stacked LSTM achieved the best performance in detecting minority botnet traffic.

---

## 🧩 Project Structure

```
botnet-detection-deep-learning/
│
├── README.md
├── botnet-detection-deep-learning-ctu13.pdf
├── notebooks/
├── src/
├── results/
└── requirements.txt
```

---

## 🚀 Key Contributions

* Designed deep learning pipeline for cybersecurity anomaly detection
* Engineered temporal and statistical network features
* Applied imbalance-aware learning strategies
* Demonstrated effectiveness of LSTM-based models for botnet detection

---

## 🛠 Tech Stack

* Python
* TensorFlow / Keras
* Scikit-learn
* Pandas & NumPy
* Matplotlib & Seaborn

---

## 📄 Research Report

Full technical report available here:

👉 **[Botnet Detection Technical Report](botnet-detection-deep-learning-ctu13.pdf)**

---

## 👨‍💻 Author

**Ahmad Zaki**
Informatics Engineering — Universitas Brawijaya

GitHub: https://github.com/ahmdzzzki

---

## 🔮 Future Work

* Real-time network deployment
* CNN–LSTM hybrid architectures
* Explainable AI (SHAP / LIME)
* Evaluation on CICIDS2017 and UNSW-NB15 datasets

---

## ⭐ If you find this project useful

Consider giving this repository a star to support the work!
