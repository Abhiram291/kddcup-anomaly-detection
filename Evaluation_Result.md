# Model Evaluation Results

## Datasets Used:
* **10% Dataset (for initial training and evaluation):** `kddcup.data_10_percent_corrected.csv`
* **Full Dataset (for final generalization testing):** `corrected.csv`

---

## Evaluation on `kddcup.data_10_percent_corrected.csv`

*(Models were trained on normal instances from this dataset. Metrics below reflect performance when evaluated on the full dataset, containing both normal and attack instances.)*

### Isolation Forest

**Summary:**
* Estimated contamination: 0.396701
* Total test samples: 29118
* True attacks in test set: 11551
* Predicted attacks: 18475

**Classification Report:**
          precision    recall  f1-score   support

  Normal       1.00      0.61      0.75     17567
  Attack       0.63      1.00      0.77     11551

accuracy                           0.76     29118
macro avg       0.81      0.80      0.76     29118
weighted avg       0.85      0.76      0.76     29118


**Confusion Matrix:**
[[10643  6924]
[    0 11551]]


**ROC AUC:** 0.9920

---

### Autoencoder

**Summary:**
* Anomaly Threshold (98th percentile of normal train MSE): 0.004486
* Total test samples: 29118
* True attacks in test set: 11551
* Predicted attacks: 11563

**Classification Report:**
          precision    recall  f1-score   support

  Normal       0.98      0.98      0.98     17567
  Attack       0.97      0.97      0.97     11551

accuracy                           0.98     29118
macro avg       0.98      0.98      0.98     29118
weighted avg       0.98      0.98      0.98     29118


**Confusion Matrix:**
[[17219   348]
[  336 11215]]


**ROC AUC:** 0.9968

---

## Evaluation on `corrected.csv` (Full Dataset)

*(Models were trained only on normal instances from `kddcup.data_10_percent_corrected.csv` and then evaluated on this unseen dataset for generalization testing.)*

### Isolation Forest

**Summary:**
* Total test samples: 77291
* True attacks in test set: 29378
* Predicted attacks: 39061

**Classification Report:**
          precision    recall  f1-score   support

  Normal       0.99      0.79      0.87     47913
  Attack       0.74      0.98      0.84     29378

accuracy                           0.86     77291
macro avg       0.86      0.88      0.86     77291
weighted avg       0.89      0.86      0.86     77291


**Confusion Matrix:**
[[37672 10241]
[  558 28820]]


**ROC AUC:** 0.9837

---

### Autoencoder

**Summary:**
* Total test samples: 77291
* True attacks in test set: 29378
* Predicted attacks: 29233

**Classification Report:**
          precision    recall  f1-score   support

  Normal       0.97      0.97      0.97     47913
  Attack       0.95      0.94      0.95     29378

accuracy                           0.96     77291
macro avg       0.96      0.96      0.96     77291
weighted avg       0.96      0.96      0.96     77291


**Confusion Matrix:**
[[46423  1490]
[ 1635 27743]]


**ROC AUC:** 0.9882

