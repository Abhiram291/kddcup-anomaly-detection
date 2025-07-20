# 🚨 Network Anomaly Detection using Unsupervised Learning (KDD Cup 1999)

## 📄 Project Overview

This project focuses on detecting unusual patterns or anomalies in network traffic using **unsupervised machine learning**. Such anomalies often signal security breaches (e.g., intrusions, DoS attacks) or system failures. We utilize the **KDD Cup 1999** dataset — a widely cited benchmark for intrusion detection.

---

## 🎯 Project Goal

To build and evaluate **unsupervised anomaly detection models** that learn only from normal traffic, simulating real-world zero-day attack scenarios where labeled attack data is unavailable during training.

---

## 🤖 Techniques Used

### 1. **Isolation Forest**
- A tree-based ensemble method that isolates anomalies using random partitions.
- Fast and effective for high-dimensional data.

### 2. **Autoencoder (Neural Network)**
- Learns to reconstruct "normal" network behavior.
- Anomalies are detected using high reconstruction error thresholds.

---

## 📁 Dataset Information

- **Training Data**: `kddcup.data_10_percent_corrected.csv` (used to extract *normal* connections)
- **Evaluation Data**: `corrected.csv` (includes unseen attack types)
- **Unlabeled Prediction Data**: `kddcup.testdata.unlabeled_10_percent.csv`

The dataset includes 41 features + 1 label. Features cover connection stats, protocol types, service, flags, and traffic characteristics.

---

## 🛠️ Project Structure

```bash
kddcup-anomaly-detection/
├── data/
│   ├── kddcup.data_10_percent_corrected.csv
│   ├── corrected.csv
│   └── kddcup.testdata.unlabeled_10_percent.csv
├── kddcup_anomaly_detection.ipynb     # Complete implementation
├── requirements.txt                   # Dependencies
├── README.md                          # Project overview
├── output/
│   ├── autoencoder_roc_curve_corrected.png
│   ├── isolation_forest_roc_curve_corrected.png
│   ├── autoencoder_loss_plot.png
│   ├── autoencoder_mse_distribution.png
│   └── kddcup_unlabeled_with_predictions.csv
