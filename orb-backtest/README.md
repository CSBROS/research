# Opening-range breakouts on ES

**Verdict: NO EDGE after costs**

## Question
Do the two most common opening-range breakout rules make money after costs?

## Data
174 RTH sessions, 2025-06-13 → 2026-10-12, every CQG print aggregated to 1-second OHLC. Stop/target ordering resolved per second (tie = stop first). 24 of 24 random trades re-derived print by print from raw rows.

## Rules
- **V1:** range 08:30–08:44:59 CT; first 5-minute close outside the range; stop 1 tick beyond the signal candle; target 0.5R; flat 15:00 CT.
- **V2:** range 08:30–08:59:59 CT; stop 1 tick beyond the opposite extreme; target 1R; flat 15:00 CT.
- **Costs (net MES):** 1 tick slippage on entry, stop and close; targets need a 1-tick trade-through; $1.50 round trip.

## Results (R per trade)
| Variant | n | Win rate | E (R) | 95% CI | t |
|---|---|---|---|---|---|
| V1 gross | 173 | 68.2% | +0.029 | −0.075 to +0.134 | 0.55 |
| V1 net MES | 173 | 65.9% | −0.058 | −0.164 to +0.049 | −1.05 |
| V2 gross | 174 | 45.4% | −0.092 | −0.219 to +0.037 | −1.40 |
| V2 net MES | 174 | 42.5% | −0.138 | −0.266 to −0.008 | −2.11 |

- Breakeven for a 0.5R target on a driftless walk is 66.7%. V1's 68.2% gross win rate is inside noise.
- **Multiple testing.** 288-cell family (range × stop × target × time × side): 0 cells with t > 2 (≈6.6 expected under independence). Best cell t = 0.94, Bonferroni p = 1.00. Empirical Bayes: between-cell variance ≤ 0, every cell shrinks to −0.083R.
- **Prop lifecycle.** Posterior-predictive Monte Carlo through two prop-firm rule sets: V1 fails 4 of 5 pre-registered criteria. Verdict: do not automate.

**Data.** Market data is licensed (CQG via Quantower, Databento, MenthorQ) and is not included. This folder holds code, pre-registrations and derived statistics only. Every script reads from a local data path set in its header.
