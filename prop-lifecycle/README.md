# What a prop-firm evaluation pays at zero edge

**Verdict: MODEL**

## Question
How much of a funded-trader program's payout comes from the trader, and how much from the account structure?

## Method
Vectorized Monte Carlo of the full lifecycle (evaluation → funded → payouts → breach), posterior-predictive edge, weekly block bootstrap, common random numbers against a zero-edge arm.

## Results
- **Barrier geometry.** At zero edge, P(pass) ≈ exp(−T/D): 28.7% closed form vs 29.0% simulated, for any reward-to-risk and any risk unit between 10–30% of the drawdown.
- **Sample size.** 50 lifecycles cannot rank configurations: a true 4.1× gross multiple has a 90% interval of 1.2×–7.7× over 50 evaluations; ±0.5× needs ~2,000.
- **Decomposition.** A published playbook's 37% pass / 35% payout / 4.2× figures are reproduced only with +0.075 to +0.125R per trade of edge. The same sizing at zero edge gives ~1.9–2.5×: about half the multiple is the firm underwriting the drawdown.
- **Zero-drift conservation.** E[withdrawals per funded account] = start − E[balance at termination] ≤ D. Edge is monetized through expected trades survived.

Rule sets are taken from third-party summaries and should be checked against each firm's current terms.
