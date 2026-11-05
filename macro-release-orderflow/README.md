# A 10-second order-flow signal after macro releases

**Verdict: FALSIFIED by independent replication**

## Question
Does the one-sidedness of aggressor volume in the first 10 seconds after a 07:30 CT release predict the next two minutes of ES?

## Signal and rule
`c10 = (buy − sell) / volume` over 07:30:00–07:30:09, signed by the 10-second price move.
Trade only if the 10-second move is ≥ 4 points. Follow if `c10 ≥ 0.25`, fade if below. Stop 10 points, exit at 07:32:10.
Fills: first opposite-aggressor print after decision + latency; commission 0.30 points round trip.

## Results
| Sample | n | Points / trade | t | Note |
|---|---|---|---|---|
| In sample, all 07:30 impulses, 50 ms | 22 | +2.64 | 1.63 | annualized Sharpe 1.90 |
| Holdout releases (08:45 / 09:00 / 13:00) | 29 | −0.96 | — | same rule, same spike filter |
| Independent replication, ES, all 07:30 | 198 | −1.41 | −1.47 | Databento MBP-1, 2018–2026, quote fills |
| Independent replication, NQ, all 07:30 | 220 | −2.29 | −0.85 | |

- **Parameter audit.** The chosen cell (10 s, 0.25, 120 s, 4 pt) ranked 37 of a 560-cell grid on our data. Deflated Sharpe (N = 560) = 0.05.
- **Signal decay.** Spearman correlation of c10 with the next 120 s: +0.28 in our window, +0.041 (p = 0.56) in the replication.
- **Replication fidelity.** The collaborator's implementation reproduced our trades on 21 of 22 days with identical c10 values before the holdout was scored.

## Verdict
Edge rating F. The rule is retired. A Sharpe of 1.9 on 22 events chosen from 560 configurations is what chance produces.

## Credit
Independent replication: **Limbø**, on his own Databento GLBX.MDP3 MBP-1 data, from a spec frozen and hashed before he ran it.

**Data.** Market data is licensed (CQG via Quantower, Databento, MenthorQ) and is not included. This folder holds code, pre-registrations and derived statistics only. Every script reads from a local data path set in its header.
