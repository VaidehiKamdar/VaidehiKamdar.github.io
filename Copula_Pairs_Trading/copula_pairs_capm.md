
---
layout: default
title: "Copula Pairs Trading Combined with CAPM"
---

# Copula Pairs Trading Combined with CAPM Model

## Overview

This project implements a **copula-based pairs trading strategy** enhanced by **CAPM-driven stock ranking** for asset selection. Executed on a live simulator using **QuantConnect + Interactive Brokers** from Feb 1 to Apr 30, 2024, the strategy combines **statistical arbitrage** with **fundamental analysis** to generate risk-adjusted alpha.

By fusing non-linear dependency modeling (via copulas) with CAPM (for systematic risk assessment), the framework captures relative mispricings and builds a market-neutral portfolio with strong return characteristics.

---

## Tools & Techniques

### 📊 Statistical Modeling
- **Copulas**: Clayton, Frank, Gumbel for tail dependency
- **AIC**: Model selection and goodness-of-fit assessment

### 📉 Financial Modeling
- **CAPM Regression**:
  - Alpha generation and beta estimation
  - Benchmarks: SPY, DIA
- **Linear Regression**: Rolling historical beta computation

### 🧩 Portfolio Construction
- Equal weighting for diversification
- Long-short positions based on pair signals
- Universe: Dow 30 + Sector ETFs

### ⚖️ Risk Management
- Pairs trading structure ensures market neutrality
- Rolling rebalancing to adapt to price relationships
- Slippage minimization through immediate execution

---

## Methodology

### 1. **Universe Selection**
- Dynamic selection from:
  - Dow Jones 30 constituents
  - Sector ETFs (Tech, Healthcare, Industrials)
  - Manually selected growth/tech stocks

### 2. **Copula Modeling**
- Fit multiple copula functions to asset pairs
- Use AIC to select best-fit model
- Generate trading signals from deviation in dependency structure

### 3. **CAPM Alpha Ranking**
- Estimate alphas and betas using historical regression
- Rank stocks based on excess return over benchmark
- Select undervalued stocks with strong performance metrics

### 4. **Execution & Allocation**
- Long underpriced asset, short overpriced pair
- Equal capital allocation
- Rebalanced upon signal confirmation

---

## Key Insights

- **Portfolio Value**: $1,109,326.76 → **+11.09% in 3 months**
- **Annualized Return**: 54.28%
- **Sharpe Ratio**: 1.36
- **Max Drawdown**: 5.55% (tight risk control)
- **Top Sector**: Tech (8.74% contribution)
- **Asset Split**: 56.66% equity exposure, balanced long/short

---

## Visuals

![NAV Performance](/indeximages/copula_nav.png)

*Net Asset Value progression: March rally, April volatility*

---

![Portfolio Allocation](/indeximages/copula_allocation.png)

*Final portfolio sector and ticker-wise distribution*

---

## Summary

This project validates the effectiveness of **copulas** in identifying tradeable pairwise mispricings and **CAPM alpha filtering** to improve portfolio performance. Achieving over 11% return in 3 months with a Sharpe of 1.36, the strategy balances statistical rigor with financial intuition. The live execution results and robust performance make it applicable for systematic hedge funds or quantitative portfolio managers.

---

📂 [Return to Portfolio Home](/)
