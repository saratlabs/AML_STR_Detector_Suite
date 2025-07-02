# AML_STR_Detector_ML_V2 – Unsupervised Anomaly Detection using Isolation Forest

This project is a machine learning–based Anti-Money Laundering (AML) detection system that simulates customer transactions and flags anomalies using the Isolation Forest algorithm. It serves as the second phase of the AML_STR_Detector series, offering an intelligent upgrade over rule-based systems.

---

## Project Objective

Detect potentially suspicious financial transactions using **unsupervised anomaly detection**. The goal is to mimic real-world AML detection practices and generate alert-ready outputs for further compliance review and STR filing.

---

## Workflow Overview

1. **Synthetic Dataset Generation**
   - 500 customer transactions created with attributes like amount, risk band, country, channel, and frequency.

2. **Data Preprocessing**
   - Encoded categorical features (e.g., transaction type, customer risk band)
   - Removed identifiers and scaled the feature space

3. **Model Training**
   - Trained Isolation Forest on transaction data
   - Used 5% contamination to simulate abnormal activity threshold

4. **Anomaly Detection**
   - Flagged 25 transactions as anomalous
   - Appended anomaly score and flags to main dataset

5. **Alert Generation**
   - For each anomalous transaction:
     - Unique Alert ID
     - Red Flags & Risk Score
     - Compliance References (FATF, Basel, BaFin)
     - STR Filing Status
     - Timestamp

6. **Excel Export**
   - All alerts exported to `ml_alerts_output.xlsx`

---

## Repository Contents

| File                        | Description |
|-----------------------------|-------------|
| `ml_engine.ipynb`           | Full notebook: data simulation → ML detection → STR export |
| `synthetic_transactions.csv`| Synthetic input dataset |
| `ml_alerts_output.xlsx`     | Excel report of anomalous transactions flagged for STR |
| `README.md`                 | This documentation |

---

## Key Features

- Fully unsupervised ML (no need for labeled fraud data)
- Realistic simulation of customer activity
- End-to-end detection to alert pipeline
- FATF-compliant references with narrative generation
- Can be extended to auto-file STRs or benchmark against rule-based detection (V1)

---

## Requirements

Install dependencies using:

```bash
pip install pandas scikit-learn openpyxl

## Notes

This is a prototype and uses synthetic data.

For production, the model should be trained on real, anonymized customer data.

The system currently flags based on rarity — further investigation is required to confirm laundering.

## Related Projects
AML_STR_Detector_Lite_V1 – Rule-based AML detection system (Phase 1)

## Author
Sai Sarat Chandra
Data Science & Artificial Intelligence | FinCrime Detection | AML Systems