# EMEA Bank Analysis — Equity Research Project

Analysing three major European banks using Python. 
Built to develop financial modelling skills and 
understand how equity research analysts evaluate bank stocks.

---

## What This Project Does

It goes through the full process of a basic equity research exercise:

- Pulls three years of financial data for Barclays, BNP Paribas, 
  and Deutsche Bank using the yfinance library
- Calculates the key metrics that matter for bank analysis — NIM, 
  ROE, ROA, cost to income ratio
- Compares each bank's valuation using P/B and P/E ratios against 
  sector averages
- Runs a sensitivity analysis to quantify how much each bank's 
  earnings depend on where interest rates go
- Arrives at a written investment view for each bank

The full written output is in `investment_note.md`.

---

## The Three Banks

**Barclays (BARC.L)** — UK bank, mid-restructure, interesting because 
it showed the strongest earnings growth in 2024 despite still trading 
below book value.

**BNP Paribas (BNP.PA)** — Largest French bank, steady profitability 
but a cost efficiency problem that the market is clearly aware of.

**Deutsche Bank (DBK.DE)** — The most complex case. Operational 
improvements are real but ROE is going in the wrong direction. 
The sensitivity analysis reveals it is also the most vulnerable 
to ECB rate cuts — one 25bps move pushes it close to breakeven.

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

## Key Findings

**Barclays** had the best 2024 of the three — 19.9% net income growth, 
cost to income down to 60.9%, and ROE approaching the 10% benchmark. 
The valuation does not fully reflect this momentum yet.

**BNP Paribas** is the most profitable on ROE at 9.1% but the cost 
to income ratio above 72% is a real drag. The market discount versus 
Barclays looks justified until costs improve.

**Deutsche Bank** is the most complicated. Costs have improved 
significantly but ROE has fallen from 7.8% to 4.3% over three years — 
a revenue problem, not a cost problem. The sensitivity analysis showed 
that a single 25bps NIM compression would push net income into negative 
territory. Cheap on P/B at 0.58x but cheap for a reason.

---

## Sensitivity Analysis

The core question I wanted to answer was how much each bank's earnings 
depend on interest rates. I quantified this using:

**Income Impact = Total Assets × NIM Change**

This is a simplified upper bound — it assumes the full balance sheet 
reprices immediately which overstates true sensitivity. But the 
direction is clear: Deutsche Bank is most exposed to further ECB 
cuts, BNP has the highest absolute sensitivity due to its balance 
sheet size, and Barclays is best positioned to weather a falling 
rate environment.

| Scenario | Barclays | BNP Paribas | Deutsche Bank |
|----------|----------|-------------|---------------|
| Bear -25bps | £2.5bn | €4.9bn | €-0.1bn |
| Base Case | £6.3bn | €11.7bn | €3.4bn |
| Bull +25bps | £10.1bn | €18.5bn | €6.8bn |

---

## Tools Used

- Python — pandas, matplotlib, seaborn, numpy
- yfinance — financial data via Yahoo Finance
- Jupyter Notebooks in VS Code

---

## Limitations Worth Knowing

Yahoo Finance data is reliable for this kind of analysis but not 
Bloomberg quality. A few things required manual fixes — Barclays 
price data came in pence not pounds, and Deutsche Bank operating 
expense had to be reconstructed from component lines because it 
is not reported as a single field.

The NIM figures I calculated will not match bank-reported NIM 
exactly because I used total assets as the denominator rather 
than average interest-earning assets. The sensitivity analysis 
overstates rate sensitivity for the same reason — true sensitivity 
would be lower once you account for fixed rate assets and hedging.

---

## Investment Views

| Bank | View |
|------|------|
| Barclays | Outperform |
| BNP Paribas | Neutral |
| Deutsche Bank | Neutral to Underperform |

Full reasoning in `investment_note.md`.