# 📊 Sentiment-Driven Quantitative Trading Model

### Limit–Continuity–Discontinuity Framework for Stock Prediction

---

## 🚀 Overview

This project implements a **quantitative trading model** that integrates **news sentiment analysis with mathematical concepts** such as:

* **Limit (Trend)**
* **Continuity (Stability)**
* **Discontinuity (Shock events)**

The model predicts **future stock returns (T+5 horizon)** and generates **trading signals using a ranking-based strategy**.

---

## 🎯 Objective

Traditional models rely only on price-based indicators. This project introduces a **novel framework**:

> 📌 Convert mathematical concepts (Limit, Continuity) into ML features
> 📌 Use sentiment dynamics to predict market movement
> 📌 Build a **signal-based trading system**, not just a classifier

---

## 🧠 Core Concepts Mapping

| Mathematical Concept | Financial Interpretation     | Feature Used                           |
| -------------------- | ---------------------------- | -------------------------------------- |
| Limit                | Trend direction of sentiment | `sent_mean20`, `limit_trend`           |
| Continuity           | Stability of sentiment       | `continuity_score`, `continuity_local` |
| Discontinuity        | Sudden market/news shock     | `sentiment_shock`, `strong_shock`      |

---

## 📂 Dataset

The dataset contains:

* News sentiment features (FinBERT / aggregated)
* Lagged sentiment values
* Momentum indicators
* Volatility measures
* Future returns (`return_t+1`, `return_t+3`, `return_t+5`)

---

## ⚙️ Feature Engineering

### 🔹 Limit (Trend)

* Rolling mean of sentiment
* Trend change using difference

### 🔹 Continuity (Smoothness)

* Inverse of sentiment variance
* Local change in sentiment

### 🔹 Discontinuity (Shock Detection)

* Sentiment spikes
* Volatility-triggered shocks

---

## 🏗️ Model Pipeline

```text
Raw Sentiment Data
        ↓
Feature Engineering (Limit + Continuity + Shock)
        ↓
Class Imbalance Handling (Downsampling)
        ↓
Random Forest Model
        ↓
Probability Output
        ↓
Ranking (Top Signals)
        ↓
Trade Execution
```

---

## 🤖 Model Details

* Algorithm: **Random Forest Classifier**
* Handling Imbalance:

  * Downsampling
  * Class weighting
* Prediction Type:

  * Binary classification (Up/Down)
* Strategy:

  * **Ranking-based (Top 25% signals)**

---

## 📈 Trading Strategy

Instead of relying on raw predictions:

* Rank predictions based on probability
* Trade only **top confidence signals**
* Apply filters:

  * Positive trend (limit)
  * High continuity (stability)

---

## 📊 Evaluation Metrics

### Machine Learning:

* Precision
* Recall
* F1 Score

### Trading:

* Cumulative Returns
* Signal Quality

---

## 💡 Key Insights

* Accuracy is NOT the goal → **Profitability is**
* Sentiment works better for **medium-term horizons (T+5)**
* Combining:

  * Trend (Limit)
  * Stability (Continuity)
  * Shock (Discontinuity)

👉 Creates a **powerful alpha signal**

---

## 🔥 Results (Example)

* Moderate classification accuracy (~45–55%)
* Strong trading performance (2x–9x returns depending on configuration)
* High-quality selective trading signals

---

## 🧪 Future Improvements

* XGBoost / LightGBM models
* LSTM / Transformer for time-series
* Walk-forward validation
* Sharpe ratio & risk metrics
* Real-time sentiment ingestion

---

## 📌 Research Contribution

This project introduces a **novel interdisciplinary approach**:

> 🔬 Applying calculus concepts (Limit & Continuity) to financial ML

It bridges:

* Mathematics
* Machine Learning
* Quantitative Finance

---

## 🧑‍💻 Author

**Kamal Gavel**

* Quantitative Finance Researcher
* Machine Learning Practitioner
* Focus: Algorithmic Trading & AI in Finance

---

## ⭐ Final Thought

> This is not just a prediction model —
> it is a **signal-driven trading system** built on mathematical intuition.

---
