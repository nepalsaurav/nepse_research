

# NEPSE Stock Direction Prediction using Machine Learning

This repository contains the implementation and experiments for a research study on predicting next-day stock direction in the Nepal Stock Exchange (NEPSE) using machine learning models and technical indicators.

The project focuses on comparing traditional, ensemble, and deep learning models under realistic trading constraints, including T+2 settlement and stop-loss risk management.

---

## Research Paper

The full research paper is available on arXiv:

**[Link will be added after publication]**

**Title:**
*Comparative Analysis of Machine Learning Models for NEPSE Stock Direction Prediction Using Technical Indicators*

---

This project investigates:

> **How effective are Logistic Regression, XGBoost, and LSTM models in predicting next-day stock direction in NEPSE using technical indicators?**

---

## Dataset

* **Stocks Used:**

  * NABIL (Banking)
  * NICA (Banking)
  * UPPER (Hydropower)
  * SHIVM (Manufacturing)

* **Data Type:**

  * Daily OHLCV (Open, High, Low, Close, Volume)

* **Structure:**

```text
date, open, high, low, close, volume
```

---

## ⚙️ Features

Technical indicators derived from price and volume data:

* Daily Returns
* SMA (5, 20)
* EMA (10)
* RSI (14)
* MACD
* Bollinger Bands
* Volume Change
* Rolling Volatility

---

## Target Variable

Binary classification:

```text
1 → Next-day price increases  
0 → Next-day price decreases or stays the same
```

---

## Models

The following models are evaluated:

* Logistic Regression (baseline)
* XGBoost (tree-based ensemble)
* LSTM (time-series deep learning)

---

## Experimental Setup

* Chronological train-test split (no data leakage)
* Same feature set across all models
* Experiments conducted separately for each stock

---

## Backtesting Strategy

A realistic trading strategy is implemented with NEPSE constraints:

### Rules

* Buy when model predicts upward movement
* Hold position until exit condition is met
* No short selling

### Constraints

* **T+2 settlement:** positions cannot be sold before 2 trading days
* **Stop-loss:** fixed threshold (e.g., 3%) to limit downside risk

### Metrics

* Cumulative Return
* Sharpe Ratio
* Maximum Drawdown

---
