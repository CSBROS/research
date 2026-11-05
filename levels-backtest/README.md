# Do gamma-map levels hold?

**Verdict: NOT SUPPORTED**

## Question
Do price levels from the daily dealer-gamma map reject price more often than arbitrary prices?

## Grade test
- Unit: a touch of a graded level after the map is live. Hold = 8 points back before 4 points through (random walk ≈ 33%). Six definitions run.
- Controls: a 5-point grid and 25 random off-grid prices per session, more than 3 points from any map level.

| | Touches | Held |
|---|---|---|
| Map levels (50 levels) | 204 | 33.3% |
| Random prices | 1,444 | 36.4% |
| 5-point grid | — | 35.8% |

Difference −3.0 points, 90% CI −11.6 to +6.1. Grade vs hold rank correlation +0.06 (one-sided p 0.23).

## Setup backtest
All 55 tradeable setups from 21 map files, limit entries, live risk-calculator rules (Python port, parity 3,000/3,000 with the compiled C#), 25/25 trades verified against raw prints.
BASE: 25 trades, −0.134R mean (t −0.54). Neither touch-vs-through fills nor the attempt limit changed the result.

## Verdict
No standalone level edge in this sample, and the grade does not sort levels. Any edge must sit in the trigger (order flow at the level).

**Data.** Market data is licensed (CQG via Quantower, Databento, MenthorQ) and is not included. This folder holds code, pre-registrations and derived statistics only. Every script reads from a local data path set in its header.
