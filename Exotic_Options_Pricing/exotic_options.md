---
layout: default
title: "Exotic Option Pricing and Strategies"
---

# Exotic Option Pricing and Strategies

## Overview

This project explores the pricing of exotic options—including Rainbow, Chooser, and Forex options—using a variety of stochastic models. We aim to compare methods, validate pricing consistency across models, and test theoretical hedging strategies such as static replication and multi-asset min-max parity.

The project is broken into three main sections:
- Rainbow options (basket options on max/min underlying)
- FX options (USD/JPY) using stochastic volatility
- Chooser options (flexible call/put decision at future point)

## Tools & Techniques

- **Models Used**:
  - Monte Carlo Simulation with Correlated GBM
  - Ornstein-Uhlenbeck Process
  - Cox-Ross-Rubinstein (CRR) Binomial Model
  - Kou Jump Diffusion Model
  - Heston Stochastic Volatility Model
  - Garman-Kohlhagen Model for FX options

- **Programming**: Python
- **Data**: Bloomberg, FRED, Japan Ministry of Finance
- **Mathematics**: SDEs, Calibration, Numerical Integration

## Key Highlights

- Verified **min-max parity** in rainbow options:  
  $$C_{max}(S_1, S_2, K) + C_{min}(S_1, S_2, K) \approx C(S_1, K) + C(S_2, K)$$
  with minor deviations during high-volatility periods (e.g. 2020 pandemic, 2023 debt ceiling).

- Calibrated Heston model using real FX data for USD/JPY  
  → Captured volatility smile/skew more accurately than Garman-Kohlhagen.

- Developed **Chooser-FX trading strategy**:
  - Compared payoff paths
  - Long FX, long/short chooser depending on projected margins
  - Hedged downside risk while capturing convex payoffs.

## Visuals

### Rainbow Option Pricing & Replication
![Rainbow Option Pricing](/indeximages/exoticoptionprice.png)

### Chooser Option Model Prices
*CRR vs. Kou Jump Diffusion — divergence in high-volatility environments.*

### Profit/Loss of Combined FX-Chooser Strategy
*A hedged position to exploit directional and volatility asymmetry.*

## Summary

This project blends advanced derivatives modeling with practical hedging techniques. It highlights the limitations of closed-form pricing models and emphasizes the importance of calibration and robustness in exotic option strategies.

---

📂 [Return to Portfolio Home](/)
