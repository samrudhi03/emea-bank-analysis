# EMEA Banking Sector — Equity Research & NIM Sensitivity Analysis

Analysis of Barclays, BNP Paribas, and Deutsche Bank across ratio analysis,
valuation, NIM sensitivity modelling, and written investment views.
Built as a structured, end-to-end research exercise using Python and Excel.

---

## Project Structure
```
emea-bank-analysis/
│
├── notebooks/
│   ├── 01_data_collection.ipynb       # Pull and validate data from yfinance
│   ├── 02_ratio_analysis.ipynb        # Calculate and chart key metrics
│   ├── 03_valuation.ipynb             # P/B, P/E, ROE vs P/B scatter analysis
│   └── 04_sensitivity_analysis.ipynb  # NIM sensitivity across rate scenarios
│
├── data/                              # CSVs saved from each notebook
├── outputs/                           # All charts saved as PNG
├── investment_note.md                 # Written research note
└── README.md
```

---

---

## What This Project Does

### 01 — Data Collection
Pulls three years of financial data for all three banks via `yfinance`: daily
share prices, income statements, balance sheets, and valuation metrics. Includes
explicit data quality checks with warnings for missing values.

Two data issues were caught and resolved:
- **Barclays price denominated in pence**, not pounds, causing a nonsensical
  P/B ratio of ~79x. Fixed by dividing price by 100 before calculating P/B.
- **Deutsche Bank does not report a single Operating Expense field.** OpEx was
  reconstructed by summing SG&A and Other Non-Interest Expense component lines.

### 02 - Ratio Analysis
Calculates NIM, ROE, ROA, Cost-to-Income, and Net Income Growth across 2022–2024
for all three banks. Uses a standardised 3-year window (2022–2024) to ensure
like-for-like comparison. Produces four time-series charts plus a 2×2 dashboard.

### 03 - Valuation
Compares each bank on P/B and P/E ratios against European sector averages.
Central chart is an ROE vs P/B scatter plot with four labelled quadrants
(undervalued, overvalued, fairly valued, value trap) to assess whether market
pricing reflects fundamentals.

### 04 - Sensitivity Analysis
Models three NIM scenarios (Bear -25bps, Base, Bull +25bps) and a continuous
range from -50bps to +50bps. For each scenario, recalculates Net Income and ROE
using:

> **Income Impact = Total Assets × NIM Change**

This is an upper bound estimate - it assumes full balance sheet repricing
rather than accounting for fixed rate assets or hedging.

---

## Excel NIM Model

A multi sheet sensitivity model built in Excel to accompany the Python analysis.

| Sheet | Contents |
|---|---|
| Assumptions | Scenario toggle (Bear/Base/Bull), central bank rates, bank level deposit beta, repricing lag, tax |
| Calc_Barclays / Calc_BNP / Calc_Deutsche | Per bank FY24A vs FY25E P&L with NIM-driven projections |
| Sensitivity | ROE grids: ΔRate × deposit β for all three banks, with heatmap |
| Scenarios | Bear/Base/Bull FY25E outputs side by side |
| Chartbook | Net Income by scenario, historical ROE/NIM, FY24 Cost to Income |
| Source Data | Raw income statements, balance sheets, price history, metrics snapshot |

The model uses cross sheet formula links, a single scenario toggle cell in
Assumptions, and colour coded inputs (hardcoded / formula / cross sheet link).

---

## Key Findings

**Barclays** - strongest 2024 performance with 19.9% net income growth, ROE
approaching the 10% benchmark, and cost to income improving to 60.9%. Valuation
does not yet fully reflect this momentum. View: **Outperform**

**BNP Paribas** - highest ROE of the three at 9.1% but cost to income above 72%
is a persistent drag. Market discount versus Barclays appears justified until
the cost base improves. View: **Neutral**

**Deutsche Bank** - ROE has fallen from 7.8% to 4.3% over three years despite
genuine cost improvements, pointing to a revenue problem rather than a cost
problem. Sensitivity analysis shows that a single 25bps ECB cut in the bear
case pushes net income close to breakeven. Cheap on P/B at 0.58x but cheap
for a reason. View: **Neutral to Underperform**

---

## Tools & Dependencies

- Python: `pandas`, `matplotlib`, `seaborn`, `numpy`, `yfinance`, `openpyxl`
- Jupyter Notebooks (VS Code)
- Microsoft Excel

```bash
pip install yfinance pandas matplotlib seaborn openpyxl jupyter
```

---

## Limitations

- Yahoo Finance data is adequate for this analysis but not Bloomberg-quality.
  Several manual corrections were required (noted above).
- NIM figures will not match bank-reported NIM exactly - total assets is used
  as the denominator rather than average interest-earning assets.
- The sensitivity analysis overstates rate sensitivity by assuming full balance
  sheet repricing; true sensitivity would be lower once hedging and fixed-rate
  assets are accounted for.

---

## Data Source

IMF World Economic Outlook Database, April 2025
Company annual reports via Yahoo Finance
