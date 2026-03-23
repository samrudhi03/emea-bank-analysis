# Equity Research Note
**Date:** March 2025  
**Banks Covered:** Barclays (BARC.L), BNP Paribas (BNP.PA), Deutsche Bank (DBK.DE)  
**Data:** Yahoo Finance via yfinance  
**Period:** FY2022 - FY2024  

---

## Why I Did This

I built this project to understand how equity research analysts actually 
think about banks. Rather than just reading about it, I wanted to go 
through the process myself - pull real data, calculate the metrics that 
actually matter, and arrive at a view I could defend.

The three banks I picked give a reasonable cross-section of European 
banking - a UK bank mid-restructure, a large French retail bank, and a 
German bank that has been trying to turn itself around for years. All 
three are interesting for different reasons.

---

## What the Numbers Show

The headline story from 2022 to 2024 is that European banks have had 
a good run. Rising interest rates meant banks could charge more on 
loans without paying much more on deposits that gap, the Net Interest 
Margin, is basically how banks make money. All three banks benefited.

But 2024 is where it gets interesting. The ECB started cutting rates. 
That tailwind is now turning into a headwind. The question I tried to 
answer is how exposed is each bank to that shift, and is the current 
stock price already reflecting it?

---

## Key Metrics — FY2024

| Metric | Barclays | BNP Paribas | Deutsche Bank |
|--------|----------|-------------|---------------|
| NIM (%) | 0.85 | 0.72 | 0.94 |
| ROE (%) | 8.8 | 9.1 | 4.3 |
| Cost to Income (%) | 60.9 | 72.0 | 60.0 |
| Net Income (bn) | £6.3 | €11.7 | €3.4 |
| P/B Ratio | 0.80x | 0.79x | 0.58x |
| P/E Ratio | 8.9x | 8.0x | 8.0x |

All three banks trade below book value. That is actually a well known 
feature of European banking and it basically means the market does not 
fully trust the value sitting on their balance sheets, or does not 
believe they can earn enough on it going forward.

---

## Barclays — Outperform

Barclays had the best year of the three in 2024. Net income grew 19.9%, 
cost to income came in at 60.9% which is genuinely lean for a bank this 
size, and there are signs the restructuring is actually working.

The valuation does not fully reflect this yet. At 0.80x P/B it is 
trading roughly in line with peers, but if ROE keeps moving toward 10% 
there is a case for a re-rating. It is not cheap but it has momentum 
that the other two do not.

Main risk is the Bank of England cutting faster than expected. Barclays 
has a big balance sheet and NIM compression would hurt earnings. My 
sensitivity analysis suggests a 25bps NIM fall could knock about £3.8bn 
off net income though that is probably an overestimate since not 
every asset reprices immediately.

**View: Outperform**

---

## BNP Paribas — Neutral

BNP is the most profitable of the three on an ROE basis at 9.1% and 
has the biggest balance sheet at around €2,700bn. Revenue has grown 
steadily. On paper it looks good.

The problem is the cost to income ratio sitting at 72%. That means 
for every euro BNP earns, 72 cents goes on running the bank. The 
sector average is around 65% and anything above 70% is generally 
considered inefficient. BNP has been above that threshold for the 
entire period I looked at and the improvement has been slow.

The market seems to be pricing this in already BNP trades at a 
slight discount to Barclays despite having higher ROE. Until costs 
come down more convincingly I think that discount is fair.

**View: Neutral**

---

## Deutsche Bank — Neutral to Underperform

This is the most complicated one. On the surface Deutsche Bank looks 
cheap at 0.58x P/B - well below peers and well below book value. But 
cheap for a reason is not the same as undervalued.

The operational story is actually positive. Cost to income improved 
from 66% in 2022 to 60% in 2024 the biggest improvement of the three. 
The restructuring is clearly doing something on the cost side.

The problem is ROE. It has gone from 7.8% in 2022 to 4.3% in 2024, 
moving in the opposite direction to Barclays and BNP. Costs are 
improving but revenue is not keeping up. That is a harder problem 
to fix than a cost problem.

The sensitivity analysis makes this even more uncomfortable. A single 
25bps NIM compression would push Deutsche Bank net income into 
negative territory the only bank in this analysis where one rate 
cut could wipe out profitability entirely. That makes the investment 
case very binary. If rates stay flat or rise, there is a recovery 
story. If the ECB keeps cutting, the numbers get very difficult very 
quickly.

**View: Neutral to Underperform**

---

## Sensitivity Analysis

I wanted to quantify how much each bank's earnings depend on where 
interest rates go. The approach was simple if NIM moves by 25 basis 
points (one standard rate move), the income impact is roughly:

**Total Assets × NIM Change**

This overstates the true sensitivity because not all assets reprice 
at the same speed. Fixed rate loans do not change immediately. So 
treat these as directional upper bounds rather than precise forecasts.

| Scenario | Barclays | BNP Paribas | Deutsche Bank |
|----------|----------|-------------|---------------|
| Bear -25bps | £2.5bn | €4.9bn | €-0.1bn |
| Base Case | £6.3bn | €11.7bn | €3.4bn |
| Bull +25bps | £10.1bn | €18.5bn | €6.8bn |

The Deutsche Bank bear case is the most striking finding. A single 
rate cut effectively eliminates profitability. Every other bank stays 
comfortably positive. That asymmetric downside is the main reason I 
am cautious on Deutsche Bank despite how cheap the valuation looks.

---

## Final View

| Bank | View |
|------|------|
| Barclays | Outperform |
| BNP Paribas | Neutral |
| Deutsche Bank | Neutral to Underperform |

Barclays is the clearest case. It has momentum, it is operationally 
efficient, and it is not obviously expensive. BNP is fine but the cost 
problem is real and limits upside. Deutsche Bank is the most 
interesting intellectually but also the most dangerous the 
operational improvement is real but the earnings fragility in a 
falling rate environment makes it hard to recommend with conviction.

---

## Limitations

A few things worth being honest about:

The data came from Yahoo Finance which is free and generally reliable 
but not Bloomberg quality. Barclays price data came in pence not pounds 
which required a manual correction. Deutsche Bank operating expense 
was not reported as a single line item so I reconstructed it from 
component cost lines that introduces some approximation.

The NIM I calculated is Net Interest Income divided by Total Assets. 
Bank annual reports use a slightly different version based on average 
interest-earning assets rather than total assets, so my NIM figures 
will not match their reported numbers exactly.

The sensitivity analysis is a linear upper bound. The actual earnings 
impact of a rate move would be lower in practice because banks manage 
their interest rate exposure through hedging and asset-liability 
management. But the directional conclusions that Deutsche Bank is 
most exposed and Barclays least should hold regardless.

---

*analytical project. Not investment advice.*
