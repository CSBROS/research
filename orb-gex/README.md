# Opening-range breakout × dealer-gamma map

**Verdict: NOT SUPPORTED (pre-registered)**

## Question
Do breakouts pay more when dealers are short gamma, and can the gamma map improve either ORB variant?

## Design
Pre-registered and SHA-256 hashed before any GEX-conditioned outcome was computed. 18 sessions with a frozen pre-open map and complete tape. Four rules on V1 and V2:
G1 regime gate (negative gamma only) · G2 regime routing (break in negative, fade in positive) · G3 flip-room gate · G4 map-level target.

## Results
- 0 of 8 tests survive: every Bonferroni p = 1.00, best raw p = 0.24.
- Breakout R by gamma state at entry: V1 negative −0.036 (n 6) / positive +0.130 (n 9). The negative-gamma premise is not supported in sample.
- Minimum detectable effect 0.2–1.0R per session at α = 0.05/8, power 0.80. At the observed effect, V2 + G3 needs ~176 forward sessions.

## Forward protocol
Rules fixed as of 2026-10-12; V2 + G3 is evaluated at 176 forward sessions with nothing re-tuned.

**Data.** Market data is licensed (CQG via Quantower, Databento, MenthorQ) and is not included. This folder holds code, pre-registrations and derived statistics only. Every script reads from a local data path set in its header.
