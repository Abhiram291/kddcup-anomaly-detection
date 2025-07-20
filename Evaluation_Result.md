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
