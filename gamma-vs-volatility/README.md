# Does the gamma board forecast the morning?

**Verdict: DESCRIPTIVE (n = 19 board days)**

## Question
Can the pre-open dealer-gamma board say how volatile 08:30–10:15 CT will be?

## Data
54 sessions of realized volatility (16-tick bars per hour), 19 with a board classification.

## Results
| Board class | n | Median bars/hr |
|---|---|---|
| Positive | 7 | 27 |
| Negative | 7 | 39 |
| Books disagree in sign | 5 | 55 |

- First 15 minutes vs rest of morning: r = 0.77. Overnight 03:00–08:30: r = 0.40.
- A sign flip alone is not a volatility signal (flip median 38 vs 50). Three of four both-negative flip days were ordinary.
- Magnet check: the largest positive strike was reached 3 of 3 times when within ~30 points of the open, 0 of 2 when 50+ away; one clean pin in five.

**Data.** Market data is licensed (CQG via Quantower, Databento, MenthorQ) and is not included. This folder holds code, pre-registrations and derived statistics only. Every script reads from a local data path set in its header.
