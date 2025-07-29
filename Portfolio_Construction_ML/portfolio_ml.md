---
layout: default
title: "Portfolio Construction and Quantitative Trading using DBN + LSTM"
---

# Portfolio Construction and Quantitative Trading using DBN + LSTM

## Overview

This project develops an advanced portfolio management system that combines **Deep Belief Networks (DBN)** with **Long Short-Term Memory (LSTM)** models for financial time series prediction. The framework integrates deep learning-based asset price forecasting with both **Modern Portfolio Theory (MPT)** optimization and **algorithmic trading strategies**, delivering a comprehensive quantitative trading pipeline.

The approach highlights the superiority of hybrid deep learning architectures over traditional models and demonstrates practical portfolio optimization through rolling Sharpe-ratio maximization and ranked return-based strategies.

---

## Tools & Techniques

### 🧠 Deep Learning Architecture
- DBN for feature extraction and pattern recognition
- LSTM for sequential modeling and price prediction
- RBMs for unsupervised layer-wise pretraining

### 📊 Portfolio Optimization
- MPT with Sharpe ratio maximization
- CVXPY for convex optimization & efficient frontier
- Rolling quarterly rebalancing

### 📈 Technical Analysis
- OHLCV indicator integration (DMI, EMA, RSI, SMI, WMA)
- Market indices: GSPC, DJI, IXIC, NYAC, XAX

### 🏦 Trading Strategy
- Ranked-weighted return strategy
- Long-only, quarterly rebalanced portfolio

---

## Methodology

### 1. **Data Collection & Preprocessing**
- Yahoo Finance OHLCV data for Dow Jones 30 stocks
- Technical indicator calculation and normalization

### 2. **Model Architecture**
- **Model 1**: DBN → LSTM for Adjusted Close prediction
- **Model 2**: Combines OHLC and Model 1 output
- 20-day iterative forecasting
- LSTM trained using BPTT

### 3. **Portfolio Construction**
- **MPT Approach**: Long-only Sharpe-optimal optimization
- **Algo Strategy**: Rank funds by quarterly return → allocate to top 10
- Equal weighting for diversification

### 4. **Model Validation**
- Compared against Ridge Regression and XGBoost
- Metrics: SMAPE, EVS, MAE, MSLE, MSE, R²
- Backtested over 2021–2025

---

## Key Insights

- **Forecasting Superiority**: DBN+LSTM beat Ridge and XGBoost across all metrics
- **Portfolio CAGR**: 22.31% from $100,000 initial capital
- **Risk-Adjusted Return**: Sharpe ratio consistently > SPY benchmark
- **Efficient Frontier**: Optimization identified Sharpe-maximizing portfolios
- **Rolling Optimization**: Strategy held up across multiple market regimes (2021–2025)

---

## Visuals

![Model Performance Comparison](/indeximages/dbn_vs_ridge.png)

*DBN+LSTM vs Ridge and XGBoost (SMAPE, R², EVS)*

---

![Portfolio vs Benchmark](/indeximages/cumulative_returns.png)

*Cumulative returns: Optimized Portfolio vs SPY*

---

![Efficient Frontier](/indeximages/efficient_frontier.png)

*Efficient frontier with max Sharpe portfolio*

---

## Summary

This project showcases the powerful combination of deep learning and financial theory for real-world trading strategies. The DBN+LSTM hybrid model provides improved predictive accuracy, and its integration with MPT-based optimization and algorithmic strategies produces robust, risk-adjusted returns.

With a 22.31% CAGR and strong outperformance over benchmarks, this framework demonstrates scalable, intelligent portfolio construction for modern asset management.

---

📂 [Return to Portfolio Home](/)
