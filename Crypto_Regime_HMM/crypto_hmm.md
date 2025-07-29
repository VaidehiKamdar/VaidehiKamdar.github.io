---
layout: default
title: "Econometric Models & Regime Detection in Cryptocurrencies"
---

# Economics of FinTech: Econometric Models & Regime Detection in Cryptocurrencies

## Overview

This project explores the application of advanced econometric models to analyze and forecast **cryptocurrency price dynamics and volatility**, focusing on **Bitcoin, Ethereum, and Solana**. We replicate and extend key findings from academic literature using **ARCH/GARCH/EGARCH** models and introduce a novel **Hidden Markov Model (HMM)**-based framework for volatility regime classification.

The study integrates traditional financial modeling with modern machine learning to provide insights into volatility clustering, persistence, and regime-switching behavior unique to digital assets.

---

## Tools & Techniques

### 📈 Econometric Models
- **ARCH / GARCH(1,1)**: Volatility clustering
- **EGARCH**: Asymmetric volatility capture
- **Jump-GARCH / TGARCH**: Tail risk and threshold modeling

### ⏱️ Time Series Analysis
- **ARIMA** for mean prediction
- **ADF** tests for stationarity
- **ARCH-LM** for volatility model validation

### 🤖 Machine Learning
- **Hidden Markov Models (HMM)** for regime inference
- **PCA** for dimensionality reduction
- **Viterbi Algorithm** for most probable state path

### 📊 Model Evaluation
- **AIC / BIC** for model selection
- **Rolling Window** testing
- **MSE** and confidence interval calibration

---

## Methodology

### 1. **Data Preparation**
- Daily price data for BTC (2015–2024)
- Log returns calculation and ADF test for stationarity

### 2. **Volatility Modeling**
- GARCH(1,1): Best performer (AIC = -154.23)
- EGARCH(1,1): Captures leverage effects (AIC = -152.78)
- TGARCH: Effective for asymmetry
- Jump-GARCH: Captures extreme price movements

### 3. **Hybrid ARIMA-GARCH**
- ARIMA forecasts returns; GARCH forecasts conditional variance
- Rolling forecast window and confidence interval adjustment
- Achieved MSE of 0.0018 for 1-day forecasts

### 4. **HMM Regime Detection**
- 3 regimes: Low / Medium / High volatility
- Inputs: return, volatility, price range, trading volume
- PCA-reduced data fit into HMMs for BTC, ETH, SOL
- Transition matrices reveal regime duration and transitions

---

## Key Insights

- **BTC**: High volatility regime has 83% persistence
- **ETH**: Fastest reversion to low volatility (85%)
- **SOL**: Highest volatility across all states

- **Jump variance** contributes ~60% of BTC's total variance
- **GARCH(1,1)** had strongest volatility persistence:  
  $$\alpha_1 + \beta_1 = 0.95$$
- COVID-19 period shows regime clustering across all tokens

---
