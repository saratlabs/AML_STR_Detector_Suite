# Theoretical & Regulatory Backbone of the AML_STR_Detector_Suite

This project was guided by core principles from international regulatory bodies such as **FATF**, **Basel Committee**, and **BaFin**, alongside deep banking theory and practical AI/ML methods. This document outlines all foundational elements behind our detection scenarios and red flag generation logic.

---

## Regulatory Frameworks

### FATF – Financial Action Task Force

| FATF Recommendation | Purpose | Connection to Detection |
|---------------------|---------|--------------------------|
| Rec 10 – CDD        | Know Your Customer (KYC), risk profiling | Used in scenarios with mismatched customer behavior or dormant reactivation |
| Rec 11 – Record Keeping | Maintain audit trail | Tied to `MFTAFS`, `SSDA`, `MCPT` |
| Rec 20 – STR Filing | Report suspicious activity | Triggered when red flags breach risk threshold |
| Rec 14/16 – Wire Transfers | Cross-border transfer transparency | Used in `FFMC`, `SRC_DC` |
| Rec 15 – New Technologies | AML risk with fintech/crypto | Forms base of `NCS`, AI mapping |
| Rec 22 – DNFBPs Risk Control | Controls for high-risk entities | Related to `EDD` and enhanced alerting |
| Rec 29 – FIU Role | Reporting pipeline to FIU | Final alerts mimicked STR structure |
| Rec 34 – Feedback Mechanism | Loop between banks and FIU | Alerts align with this via risk references |

---

### Basel Committee on Banking Supervision (Basel III)

| Principle | Purpose | Usage in Project |
|-----------|---------|------------------|
| Principle 1 – Governance | Board-level oversight of AML | Scenario governance metadata |
| Principle 2 – Risk Assessment | Ongoing customer + transaction risk review | Mapped with CRR and profile deviation |
| Principle 3 – Monitoring | Continuous monitoring of transactions | Isolation Forest + Rule Engine |
| Principle 4 – High-Risk Controls | Controls on crypto, shell firms | Linked to `NCS`, `TSBN`, `EDD` |
| Principle 6 – Group AML | Consistency across subsidiaries | Cross-jurisdictional STR handling (`FFMC`, `SRC_DC`) |

---

### BaFin (Germany)

- Categorizes **AML Risks** as:
  - Transaction Pattern Risk (`RFT_OB`, `RDT`)
  - Customer Risk (`MCPT`, `SSDA`)
  - Geographic & Network Risk (`SRC_DC`, `TSBN`, `FFMC`)
  - System Abuse (`MFTAFS`, `RMF`)
- Emphasizes **proportionality and escalation-based STR filing**
- Directly reflected in our **risk band mapping**, **alert severity**, and **red flag triggers**

---

## Banking Concepts Behind Detection Logic

| Concept | Description | Usage in Scenarios |
|--------|-------------|--------------------|
| **KYC/CDD/EDD** | Customer verification and risk profiling | `MCPT`, `FFMC`, `NCS`, `TSBN` |
| **Transaction Lifecycle** | Initiation → Settlement → Reconciliation | `MFTAFS`, `RMF`, `SSDA` |
| **Correspondent Banking** | Inter-bank service relationships | `SRC_DC`, `FFMC` |
| **Nested Correspondence** | Use of hidden bank layers through intermediaries | Adds risk to cross-border anomalies |
| **SWIFT/RTGS/IMPS** | Transaction channels | Analyzed as part of `channel` and `location` features |
| **Dormant Account Management** | Accounts inactive for long | `SSDA` detection rule |
| **Sanctions Screening** | OFAC, UN, EU, RBI lists | `FFMC`, `SRC_DC`, `NCS` |
| **STR (Suspicious Transaction Report)** | Filing suspicious cases with FIU | Final alert output in Excel simulates STR prep |
| **Funds Transfer Pricing (FTP)** | Cost-based value routing in banking | Underpins layering scenarios |
| **Customer Risk Rating (CRR)** | Risk band (Low, Medium, High) | Used for scoring and alert enrichment |

---

## Red Flag Indicators Mapped to Detection Scenarios

| Red Flag Type | Example Scenario Code | Indicator |
|---------------|-----------------------|-----------|
| Repetitive Flow | `RFT_OB` | Fixed-amount transfers, layering |
| Structuring/Smurfing | `SMF`, `TSBN` | Fund fragmentation |
| Velocity Abuse | `RMF`, `MFTAFS` | Rapid frequency, system abuse |
| Geographic Arbitrage | `SRC_DC`, `FFMC` | Cross-country paths |
| Dormant Account Abuse | `SSDA` | Reactivation with high value |
| Crypto/Alt Asset Entry | `NCS` | Gift cards, wallets, prepaid |

---

## Artificial Intelligence & Machine Learning Mapping

### Phase 1: Rule-Based Detection

- Logic: Trigger rules (if-then-else)
- Data: Predefined transaction profiles
- Risk Weighting: Manual
- Output: Red flag + STR Excel

### Phase 2: Unsupervised Machine Learning (Isolation Forest)

- Model: Isolation Forest (sklearn)
- Data: 500 synthetic transactions (encoded, numerical)
- Detection: Anomaly score thresholding
- Output: Structured Excel with alert metadata (risk, narrative, STR prep)

---

## Tools & Technologies

| Tool/Library       | Purpose |
|--------------------|---------|
| **Python 3.10+**   | Programming base |
| **pandas**         | Dataframes, preprocessing |
| **scikit-learn**   | Isolation Forest, encoding |
| **openpyxl**       | Excel export |
| **Jupyter Notebook** | Interactive execution and documentation |
| **GitHub**         | Hosting, versioning, portfolio visibility |

---

## Final Thought

This AML_STR_Detector_Suite bridges the gap between **financial regulations** and **data-driven intelligence**, offering a practical model of how AI can support real-world compliance workflows. From **KYC red flags** to **anomaly-based STR preparation**, the suite serves as a portfolio-grade demonstration of RegTech implementation in Data Science and AI.