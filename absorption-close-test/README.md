# Absorption flags into the close

**Verdict: MIXED: direction fails, one structural effect holds**

## Question
When a 16-tick bar closes against its own delta (an absorption flag) late in the session, does it call the next move?

## Design
Pre-registered (`PREREGISTRATION.md`, SHA-256 a6a57461…; Addendum 5 SHA-256 5d1e7b1b…). Pass bar t ≥ 2.5. Ordinary bars serve as placebo.
Pilot: 24 sessions from bar logs. Holdout: 129 clean sessions rebuilt from every trade (with aggressor) in the tick cache.

## Results
| Test | Pilot | Holdout |
|---|---|---|
| Fade the 14:30–15:00 move into 15:00–16:00 | 17/24 right, t 2.72 | t 0.08 |
| Last flag of the day, next 10 min | — | 54%, t 0.8 |
| Every flag minus placebo, next 10 min | — | +1.38 points, t 3.7 |

- **The pilot artifact.** The bar-based pilot used range-bar closes as clock prices. Those were up to an hour stale and sat at bar extremes, which builds in a reversal. With exact trade prices on the same 24 days the fade is 11 wins / 13 losses.
- **What held.** Ordinary 16-tick bars snap back 1–2 points over 10–15 minutes; absorption bars do not. The flag means "this bar is less likely to reverse", not "price goes the flag's way".

**Data.** Market data is licensed (CQG via Quantower, Databento, MenthorQ) and is not included. This folder holds code, pre-registrations and derived statistics only. Every script reads from a local data path set in its header.
