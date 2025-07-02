# AML_STR_Detector_Suite

This repository contains a multi-version Suspicious Transaction Reporting (STR) and Anti-Money Laundering (AML) detection system. It combines rule-based logic and machine learning techniques to identify potential money laundering activities from customer transaction data.

---

## Project Overview

The suite simulates realistic financial environments using synthetic datasets and implements two major AML detection strategies:

1. **Rule-Based Detection (Version 1)**  
   Focuses on known behavioral patterns and trigger-based logic inspired by FATF, Basel, and BaFin guidelines.

2. **Machine Learning-Based Detection (Version 2)**  
   Uses Isolation Forest (unsupervised anomaly detection) to identify unusual transaction behavior, forming the foundation for AI-assisted STR generation.

A third phase involving auto-classification of STRs and advanced techniques like graph learning is under consideration for future development.

---

## Repository Structure

AML_STR_Detector_Suite/
├── AML_STR_Detector_Lite_V1/
│ ├── run_engine.ipynb
│ ├── alerts_output.xlsx
│ └── README.md
│
├── AML_STR_Detector_ML_V2/
│ ├── ml_engine.ipynb
│ ├── ml_alerts_output.xlsx
│ └── README.md
│
└── README.md ← (This file)


---

## Module Status

| Module Name                   | Approach            | Status          |
|------------------------------|---------------------|-----------------|
| AML_STR_Detector_Lite_V1     | Rule-Based Logic    | Completed       |
| AML_STR_Detector_ML_V2       | Isolation Forest ML | Completed       |
| AML_STR_Detector_AI_V3       | Graph AI / NLP STRs | Under Planning  |

---

## Features Covered

- Transaction Monitoring Engine  
- Red Flag Rules (FATF-aligned)  
- Customer Risk Profiling  
- STR Metadata Generation  
- Excel-based Output Reporting  
- ML-Driven Anomaly Detection (V2)

---

## Tools & Libraries Used

- Python 3.10+  
- Jupyter Notebook  
- pandas, scikit-learn, openpyxl  
- Excel / JSON export formats  

---

## Use Cases

- FinCrime Risk Prototyping  
- RegTech Project Demonstration  
- AML Rulebook Simulation  
- Data Science + Compliance Portfolio Showcase

---

## Author

**Sai Sarat Chandra**  
*Data Science | FinCrime | Anti-Money Laundering | AI for Regulation*