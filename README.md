# QuickPay Fintech Data Analyst Assignment

## Student Information
- **Student Name:** miranki
- **Student ID:** bitsom_ftai_2601266
- **Public GitHub Repository:** [Your GitHub Repo Link Here]

---

## Project Overview

This project is a complete data analysis pipeline for QuickPay, a fintech company that processes digital payments for merchants. The assignment covers five parts:

1. **Spreadsheet Cleaning** — Data cleaning, standardization, flag generation in Excel
2. **SQL Business Analysis** — 8 business queries answering key operational questions
3. **Python Reconciliation** — Automated workflow comparing ledger vs gateway data
4. **JSON Normalization** — Flattening nested API response into tabular data
5. **Dashboard Visualization** — Looker Studio dashboard for business monitoring

---

## Tools Used

| Tool | Purpose |
|---|---|
| Python 3 (pandas, numpy, openpyxl) | Data cleaning, reconciliation, normalization |
| Excel / openpyxl | Spreadsheet workbook creation |
| SQLite (via Python) | SQL query execution and validation |
| Jupyter Notebook | Python workflow documentation |
| Looker Studio | Interactive business dashboard |
| Git / GitHub | Version control and submission |

---

## Run Instructions

### Step 1: Install dependencies
```bash
pip install pandas numpy openpyxl nbformat
```

### Step 2: Place raw files
Make sure these files are in `01_data/raw/`:
- transactions_raw.csv
- merchant_master.csv
- users.csv
- ledger.csv
- gateway.csv
- exchange_rates.csv
- api_response_sample.json

### Step 3: Run the Python notebook
```bash
cd 04_python/
jupyter notebook fintech_pipeline.ipynb
```
Run all cells from top to bottom.

### Step 4: View the spreadsheet
Open `02_spreadsheet/spreadsheet_workbook.xlsx` in Excel or LibreOffice.

### Step 5: Run SQL queries
The queries in `03_sql/analysis_queries.sql` can be run in any SQLite/PostgreSQL/MySQL environment using the `cleaned_transactions` table.

---

## Repository Structure

```
/
├── README.md
├── 01_data/
│   ├── raw/           ← Input files
│   └── processed/     ← Output files from Python pipeline
├── 02_spreadsheet/
│   ├── spreadsheet_workbook.xlsx
│   └── spreadsheet_answers.md
├── 03_sql/
│   ├── analysis_queries.sql
│   └── sql_answers.md
├── 04_python/
│   ├── fintech_pipeline.ipynb
│   └── summary_metrics.json
└── 05_visualization/
    └── dashboard_link.txt
```

---

## Key Findings

- **Total Transactions (cleaned):** 480 out of 500 raw rows
- **Total GMV (USD):** ~$1.36 million across all regions
- **Top Region by GMV:** APAC
- **Top Merchant (Captured GMV):** Razorpay ($50,331)
- **High Value Transactions:** 47
- **High Risk Transactions:** 210
- **Reconciliation Issues Found:** 100 (50 missing in gateway, 20 missing in ledger, 23 amount mismatches, 10 status mismatches)
- **Amount at Risk:** $197,319

---

## Notes

- All monetary values are reported in USD using exchange rates from `exchange_rates.csv`
- Risk scores originally given as text labels (low/medium/high) were converted to numeric equivalents (25/50/75)
- Date standardization converts all formats to ISO 8601 (YYYY-MM-DD)
