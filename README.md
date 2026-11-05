# Research

Pre-registered, tick-level research on S&P 500 and Nasdaq-100 futures. Every study is listed with its verdict, including the ones that failed.

**Site:** https://csbros.github.io

| Study | Verdict | Headline number |
|---|---|---|
| [10-second order flow after macro releases](macro-release-orderflow/) | Falsified by independent replication | t +1.63 in sample → −1.47 on 2018–26 ES |
| [Opening-range breakouts on ES](orb-backtest/) | No edge after costs | V1 −0.058R, V2 −0.138R per trade; 0 of 288 variants t > 2 |
| [ORB × dealer-gamma map](orb-gex/) | Not supported (pre-registered) | 0 of 8 tests survive Bonferroni |
| [Do gamma-map levels hold?](levels-backtest/) | Not supported | 33.3% hold vs 36.4% for random prices |
| [Absorption flags into the close](absorption-close-test/) | Mixed (pre-registered) | Direction fails; flag vs ordinary bar t 3.7 |
| [Gamma board vs morning volatility](gamma-vs-volatility/) | Descriptive | First 15 min predicts the morning, r 0.77 |
| [CPI and PPI tape anatomy](cpi-ppi-tape/) | Descriptive | First-minute range 10.7× normal |
| [Prop-firm lifecycle math](prop-lifecycle/) | Model | Zero-edge pass rate ≈ exp(−T/D) = 28.7% |

## Method
1. **Freeze the hypothesis first.** Rules, sample and pass criteria are written and SHA-256 hashed before the outcome is computed.
2. **Verify against raw prints.** Random trades are re-derived print by print before results are reported.
3. **Count every look.** Bonferroni, deflated Sharpe, empirical-Bayes shrinkage, minimum detectable effects.
4. **Replicate independently.** Different data vendor, different code, different person.
5. **Publish the failures.**

## Data and tooling
Market data is licensed (CQG via Quantower, Databento, MenthorQ, WRDS) and is not redistributed. Analysis code was written with AI assistance (Claude); every number traces to a script and raw data that can be re-run.

MIT licensed. Research, not investment advice.
