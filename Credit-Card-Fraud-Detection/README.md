# 💳 Credit Card Fraud Risk Analysis
### Power BI Interactive Dashboard | Data Analysis Project | Fintech | 

---
<img width="1080" height="1080" alt="Image" src="https://github.com/user-attachments/assets/70b72e8e-432f-4fe1-9796-006520b4f1e8" />

<img width="1080" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a6b405ae-8199-4005-afad-589bced4881d" />

<img width="1080" height="1080" alt="Image" src="https://github.com/user-attachments/assets/9a8d8486-fbf3-4af4-b051-b3d4054e1af6" />

## 📌 Project Overview

This project presents an end-to-end data analysis and visualization solution for detecting and monitoring **credit card fraud risk across India**. Using a dataset of **1,000 real-world-style transactions**, an interactive Power BI dashboard was built to help analysts and stakeholders quickly identify fraudulent patterns, high-risk states, top fraud types, and monthly trends.

> **Fraud Rate: 28.60%** | **Fraudulent Transactions: 286 / 1,000** | **Top Fraud Type: Card Not Present** | **Highest Risk State: Maharashtra**

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| Microsoft Power BI Desktop | Dashboard creation, data modelling, DAX measures |
| Power Query (M Language) | Data cleaning and transformation |
| DAX (Data Analysis Expressions) | KPI calculations and custom measures |
| Figma | Custom canvas background design |
| CSV (Excel-compatible) | Source dataset format |
| SVG / Custom Visuals | Credit card illustration and decorative elements |

---

## 📂 Project File Structure

```
Credit Card Fraud Risk Analysis/
│
├── Fraud Detection Dash.pbix               # Power BI dashboard file
├── Credit_Card_Fraud_Risk_Analysis.csv     # Source dataset (1,000 rows)
├── dashboard_canvas_background.svg         # Custom canvas background
├── credit_card_fraud_art.svg               # Credit card illustration
└── README.md                               # Project documentation
```

---

## 📊 Dataset Description

The dataset contains **1,000 synthetic but realistic** credit card transactions from across **10 Indian states**, spanning **December 2023 to November 2024**. Each record represents a single transaction with full fraud metadata.

### Column Reference

| Column Name | Data Type | Description |
|---|---|---|
| Transaction ID | Numeric | Unique identifier for each transaction |
| Customer Name | Text | Name of the cardholder |
| Merchant Name | Text | Name of the merchant/platform |
| Transaction Date | Date | Date the transaction occurred |
| Transaction Amount (INR) | Numeric | Transaction value in Indian Rupees |
| Fraud Risk | Category | Risk level: Low, Medium, High, Critical |
| Fraud Type | Category | Type of fraud method detected |
| State | Category | Indian state where transaction occurred |
| Card Type | Category | Card network: Visa, Mastercard, Amex, Rupay |
| Bank | Category | Issuing bank name |
| IsFraud | Binary (0/1) | 1 = Fraudulent transaction, 0 = Legitimate |
| Fraud Score | Numeric (0–100) | ML-style risk score for the transaction |
| Transaction Category | Category | Type of purchase (Apparel, Food, etc.) |
| Merchant Location | Text | City where merchant is based |

### Dataset Summary

| Attribute | Values |
|---|---|
| Total Records | 1,000 transactions |
| Fraudulent Records | 286 (28.60%) |
| Legitimate Records | 714 (71.40%) |
| Transaction Amount Range | INR 141 – INR 24,993 |
| Average Transaction Amount | INR 12,227 |
| Time Period | December 2023 – November 2024 |
| States Covered | Maharashtra, Karnataka, Rajasthan, West Bengal, Uttar Pradesh, Tamil Nadu, Telangana, Gujarat, Delhi, Kerala |
| Fraud Risk Levels | Low, Medium, High, Critical |
| Fraud Types | Card Not Present, Card Skimming, Identity Theft, Account Takeover, Phishing |
| Card Types | Visa, Mastercard, Amex, Rupay |
| Banks | HDFC Bank, SBI, ICICI Bank, Axis Bank, Kotak Bank, Bank of Baroda, Federal Bank, Andhra Bank, Yes Bank |
| Transaction Categories | Apparel, E-commerce, Electronics, Food Delivery, Groceries, Transportation |

---

## 📈 Dashboard Features

### KPI Cards (Top Row)
| KPI | Value |
|---|---|
| Fraudulent Transactions | 286 |
| Critical Risk Transactions | 10.70% |
| Fraudulent Transaction Amount | 3M INR |
| Fraud Rate % | 28.60% |
| Top Fraud Type | Card Not Present |

### Interactive Visualizations

- **Total Transaction Amount by Fraud Type and Transaction Category** — Horizontal stacked bar chart showing fraud volume breakdown across 6 categories
- **Total Transaction Amount by Fraud Risk** — Donut chart displaying distribution across Low / Medium / High / Critical risk levels
- **Fraudulent Transaction by State** — Vertical bar chart ranking top 10 Indian states by fraud count
- **Fraudulent Transaction by Month** — Line/area chart showing monthly fraud trend across Jan–Dec

### Filter Panel (Slicers)
- **Fraud Type** — Filter by fraud method (dropdown)
- **State** — Filter by Indian state (dropdown)
- **Merchant Name** — Filter by specific merchant (dropdown)

### Design Highlights
- Custom dark purple canvas background designed in Figma-style SVG
- Glassmorphism card panels with subtle gradient glows and ambient lighting
- Credit card SVG illustration embedded in the filter panel
- Consistent purple/violet colour theme across all visuals

---

## 🔍 Key Insights

| # | Insight | Detail |
|---|---|---|
| 1 | High overall fraud rate | 28.60% of all transactions are fraudulent — significantly above industry benchmarks |
| 2 | Card Not Present is the #1 fraud type | Online/remote transactions dominate fraud cases, suggesting weak digital authentication |
| 3 | Maharashtra leads in fraud count | 36 fraudulent transactions — highest among all 10 states |
| 4 | Low risk is the most common category | 42.42% of transactions fall under Low risk, but fraud still occurs within this band |
| 5 | December spike in fraud | Month-on-month trend shows a sharp rise in December — likely tied to festive season spending |
| 6 | E-commerce is the highest-risk category | Online shopping platforms account for the largest share of fraudulent transaction amounts |

---

## 🚀 How to Use the Dashboard

### Opening the File
1. Open **Microsoft Power BI Desktop** on your machine
2. Go to **File → Open** and select `Fraud Detection Dash.pbix`
3. The dashboard will load with all visuals and data connected

### Using the Filters
1. Use the **Fraud Type** dropdown to isolate a specific fraud method
2. Use the **State** dropdown to focus analysis on a particular Indian state
3. Use the **Merchant Name** dropdown to drill into specific merchants
4. All charts update **simultaneously** when a filter is applied

### Cross-Filtering
- Click on any **bar** in the State chart to filter all other visuals automatically
- Click a **segment** in the Donut chart to filter by that risk level
- Click the same element again to **clear** the cross-filter

---

## 👤 Author

| Field | Details |
|---|---|
| Author | Shreeya Rajagopal |
| Project Type | Data Analytics / Business Intelligence |
| Tool | Microsoft Power BI Desktop |
| Dataset | Synthetic Credit Card Transaction Data — India (2023–2024) |
| Date | March 2026 |
| Purpose | Portfolio / Data Analysis and Fintech Project |

---

*This project was created as part of a data analytics portfolio to demonstrate skills in Power BI dashboard design, DAX calculations, data modelling, and visual storytelling using real-world financial fraud scenarios.*

