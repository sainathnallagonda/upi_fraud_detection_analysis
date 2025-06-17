# UPI Transaction Fraud Detection — End-to-End EDA & Machine Learning

## Project Overview  
This project presents a complete data analysis and machine learning workflow for detecting fraudulent transactions in UPI (Unified Payments Interface) payment data.  
We explore the data, handle class imbalance, build and evaluate machine learning models, and provide recommendations for improving fraud detection.

---

## What’s Inside This Project
- Data loading, cleaning and preparation
- Exploratory Data Analysis (EDA): univariate, bivariate plots
- Outlier handling: capping transaction amounts at the 99th percentile
- Statistical testing: t-test on fraud vs non-fraud amounts
- Feature engineering: high-value flag, night transaction flag
- Modeling:
  - Random Forest with class balancing
  - SMOTE oversampling
  - XGBoost with class weighting
- Evaluation:
  - Confusion matrix
  - Precision, recall, F1-score
  - ROC-AUC score
  - Precision-recall curve and threshold tuning
- Insights and recommendations

---

## Key Insights
- The dataset is highly imbalanced (~0.2% fraud transactions).
- Transaction amount is not significantly different between fraud and non-fraud transactions (t-test p ≈ 0.99).
- All models (Random Forest, SMOTE, XGBoost) failed to detect fraud cases in the test data.
- Precision-recall threshold tuning did not yield effective cutoffs.
- Current features do not provide strong separation between fraud and non-fraud transactions.

---

## Recommendations
- Prioritize feature engineering to create stronger fraud signals (e.g., transaction frequency, time since last transaction).
- Explore anomaly detection algorithms (e.g., Isolation Forest, One-Class SVM).
- Collect additional data points (geolocation, device fingerprinting, IP anomalies).
- Apply cost-sensitive learning techniques to penalize fraud misclassification more heavily.
- Experiment with ensemble models or stacking.
- Design for real-time fraud detection (low latency, streaming).

---

## Files
- `upi_fraud_detection_analysis.ipynb` — Main notebook with code, analysis, and evaluation  
- `README.md` — Project overview  

---

## Example Metrics
| Model                  | ROC-AUC | Fraud Precision | Fraud Recall |
|-------------------------|---------|----------------|--------------|
| Random Forest (balanced) | 0.49    | 0.00           | 0.00         |
| SMOTE + Random Forest    | 0.49    | 0.00           | 0.00         |
| XGBoost (weighted)       | 0.51    | 0.00           | 0.00         |

---

## How to Run
1. Open `upi_fraud_detection_analysis.ipynb` in Google Colab.  
2. Upload the dataset or adjust the file path if using Google Drive.  
3. Run the cells sequentially.

---

## Notes
This project highlights the challenges of fraud detection in highly imbalanced datasets.  
The focus is on understanding, evaluating, and iterating on models, with a clear view toward next steps: feature engineering and anomaly detection.

---

## License
This project is open-source and available under the MIT License.
