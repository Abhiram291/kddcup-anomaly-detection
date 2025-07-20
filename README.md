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



⚙️ Installation & Dependencies

# Step 1: Create a virtual environment
python -m venv venv
source venv/bin/activate   # or venv\Scripts\activate on Windows

# Step 2: Install dependencies
pip install -r requirements.txt
Or manually install:

pip install pandas numpy scikit-learn tensorflow matplotlib seaborn


⚙️ Data Preprocessing Highlights

🔁 Duplicate Removal: Reduces overfitting
🎯 Binary Labeling: All attack types → 1, normal → 0
🔠 Categorical Encoding: One-hot encoding for protocol_type, service, flag
📏 Scaling:
StandardScaler for Isolation Forest
MinMaxScaler for Autoencoder



📈 Evaluation Results

✅ Evaluation on kddcup.data_10_percent_corrected.csv

Metric	            Isolation Forest	      Autoencoder
Precision	               0.63	               0.97
Recall	                   1.00	               0.97
F1-Score	               0.77	               0.97
ROC-AUC	                   0.9920	             0.9968


✅ Evaluation on corrected.csv (test data)
Metric	             Isolation Forest	      Autoencoder
Precision	                 0.74	               0.95
Recall	                   0.98              	 0.94
F1-Score	                 0.84	               0.95
ROC-AUC	                   0.9837	             0.9882


🔮 Predictions on Unlabeled Data

The file kddcup_unlabeled_with_predictions.csv includes:

predicted_anomaly_if: Prediction by Isolation Forest (0=Normal, 1=Anomaly)
predicted_anomaly_ae: Prediction by Autoencoder



📊 Visualizations

Plots include:

autoencoder_roc_curve_corrected.png
isolation_forest_roc_curve_corrected.png
autoencoder_loss_plot.png
autoencoder_mse_distribution.png
These help interpret model performance and threshold tuning.


💡 Key Insights

Autoencoder achieved higher precision and F1-score, reducing false positives.
Isolation Forest, while faster, had more false positives but was still effective.
Both models generalize well to unseen attacks in corrected.csv.
