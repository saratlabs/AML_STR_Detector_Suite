# AML_STR_Detector_Lite_V1

A lightweight, rule-based Anti-Money Laundering (AML) Suspicious Transaction Reporting (STR) engine designed for rapid scenario detection and alert generation. This project aligns with regulatory expectations from FATF, Basel, and BaFin (Germany).

## Key Features

- Rule-based AML detection using:
  - RDT (Round Dollar Transactions)
  - MCPT (Mismatched Customer Profile & Transaction Type)
  - SMF (Structuring / Smurfing)

- Risk scoring and alert classification
- Adjusted scoring logic for Financial Inclusion customers (to avoid over-flagging)
- STR output in multiple fields aligned with regulatory compliance
- Full Excel export for stakeholder readability and GitHub download

## STR Alert Fields (Generated Per Customer)

Each alert includes the following structured information:

- Customer ID, Name
- Risk Band
- Financial Inclusion Flag
- Onboarding Source
- Trigger Rules (and Severity)
- Adjusted Risk Score
- Alert Classification (Soft, Moderate, Hard)
- Red Flags (Behavior Indicators)
- BaFin Risk Category
- Narrative (Transaction Articulation)
- Compliance Mapping:
  - FATF Recommendations (e.g., Rec 10, 20)
  - Basel Principle 3 – Transaction Monitoring
  - BaFin Section 6 GwG – Risk Management
- STR Filing Status (Filed / Queued / Deferred)
- Transaction Channel (e.g., IMPS, NEFT)
- Timestamp of Alert

## Output Format

- `alerts_output.xlsx`: Excel workbook with alerts in tabular format
- (Optional) `alerts_output.json`: JSON output for backend integration

## How to Use

1. Clone or download this repository
2. Open `run_engine.ipynb` in Jupyter Notebook
3. Execute all cells sequentially
4. STR alerts will be printed and exported as `alerts_output.xlsx`
5. You can open the Excel file in Microsoft Excel or Google Sheets

## Recommended Use Cases

- AML Compliance Teams (Rule Testing / Review)
- Academic Demonstrations and AI-Driven AML Research
- Internal audit and transaction monitoring prototypes
- Financial Inclusion-aware fraud monitoring showcases

## Folder Structure

AML_STR_Detector_Lite_V1/
├── run_engine.ipynb # Core AML detection engine
├── alerts_output.xlsx # Final output (Excel format)
├── alerts_output.json # Optional structured export (machine-readable)
├── README.md # Project documentation


## Compliance References

- **FATF**: Recommendation 10, 20, 22, 29
- **Basel Committee**: Principle 3 – Ongoing Due Diligence and Monitoring
- **BaFin Germany**: Section 6 GwG – Risk Management (Money Laundering Act)

## License

Open-source for learning and non-commercial demonstration. Attribution required.