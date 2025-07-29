---
layout: default
title: "Dynamic Credit Migration-Based Trading Framework"
---

# Dynamic Credit Migration-Based Trading Framework

## Overview

This project develops a **daily credit scoring and trading framework** by integrating structural credit risk models with statistical state estimation. Using the **KMV model** and **Hidden Markov Models (HMMs)**, we dynamically track creditworthiness and use the output to design a **hedged CDS-equity trading strategy**.

The framework combines quantitative credit modeling with machine learning-based state inference to create responsive, data-driven credit trading signals.

## Tools & Techniques

- **Credit Modeling**:
  - KMV model (Distance to Default, Probability of Default)
  - Option-based firm valuation via Merton framework
- **Machine Learning**:
  - Hidden Markov Models (HMMs) for credit state inference
  - Viterbi algorithm for path estimation
- **Financial Ratios & Scoring**:
  - PCA-based financial health scoring
  - TOPSIS for multi-criteria decision analysis
- **Trading Strategy**:
  - CDS-Equity hedged long/short trades
  - Incorporates Credit Score + VIX for signal generation

## Methodology

1. **KMV Model**:  
   Market value of firm assets and volatility estimated using Black-Scholes Merton logic. From this, we compute:
   - Distance to Default (DD)
   - Probability of Default (PD)

2. **Hidden Markov Model (HMM)**:  
   Uses DD, PD, CDS spreads, inflation rates, and treasury yields to model transitions across 21 credit states.
   - Trained with Baum-Welch algorithm
   - Inference via Viterbi algorithm

3. **Credit Scoring System**:
   - Combines normalized HMM states + PCA-weighted financial ratios
   - Final score scaled from 0–800
   - Used to generate long/short signals

4. **Trading Strategy**:
   - Long CDS / Short Equity if credit score deteriorates
   - Weighting: 0.5 (Credit Score) and -0.5 (VIX)
   - Portfolio construction: Equal weight, Market cap weight, Mean-Variance Optimization

## Key Insights

- **KMV + HMM integration** enables real-time dynamic credit rating estimates
- **Sharpe Ratio** of 1.2 achieved with optimized hedged portfolio
- Outperformed both equal- and market cap-weighted benchmarks
- Strategy effectively balances **systemic** (VIX) and **idiosyncratic** (credit score) risk

## Visuals

![Credit Trading Strategy](/indeximages/credittrading.png)

*Cumulative return of the CDS-equity hedged strategy*

## Summary

By fusing credit risk theory with machine learning and optimization, this framework delivers a scalable, interpretable trading system. The methodology is extendable to other asset classes and real-time credit event detection.

---

📂 [Return to Portfolio Home](/)
