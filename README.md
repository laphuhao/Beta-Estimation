# Comparative Analysis of Beta Estimation Methods for Market Risk Measurement on the Vietnamese Stock Market

> **Award:** 3rd Prize - National Student Science Competition "Olympic Econometrics and Applications" VIII, 2023

---

## 📌 Overview
This research evaluates and compares three beta estimation methods under the **CAPM framework** for measuring systematic risk on the Vietnamese stock market, using daily stock data from the VN30 index.

---

## 🎯 Motivation
Traditional **Historical Beta** assumes beta is constant over time — an assumption that fails during periods of high market volatility (financial crises, COVID-19). This study investigates whether time-varying methods such as **Rolling Beta** and **Dynamic Conditional Beta (GARCH-family)** provide more accurate risk measurements.

---

## 🗂️ Data & Methodology

| | Details |
|---|---|
| **Market** | Ho Chi Minh Stock Exchange (HOSE) |
| **Stocks** | 9 VN30 constituents: HPG, FPT, DHG, DPM, GMD, KBC, MSN, PVD, REE |
| **Benchmark** | VN-Index |
| **Period** | Jan 3, 2012 – Dec 30, 2022 (2,743 observations) |
| **Data source** | Investing.com (daily closing prices) |
| **Tools** | Python · Google Colab |

---

## ⚙️ Methods Compared

| Method | Description |
|---|---|
| **Historical Beta** | Static OLS regression over full historical window — beta is constant |
| **Rolling Beta** | Time-varying beta estimated over a rolling 100-day window (quarterly) |
| **Dynamic Conditional Beta** | GARCH-family (CCC-MGARCH) model capturing time-varying volatility and conditional covariance |

---

## 📊 Key Results

**Historical Beta values (full sample 2012–2022):**

| Stock | Historical Beta |
|---|---|
| HPG | 1.211 |
| FPT | 0.914 |
| PVD | 0.804 |
| KBC | 0.706 |
| GMD | 0.637 |
| MSN | 0.584 |
| DPM | 0.565 |
| REE | 0.554 |
| DHG | 0.240 |

**GARCH model parameters (selected):**

| Stock | Model | alpha[1] | beta[1] | gamma[1] |
|---|---|---|---|---|
| HPG | GJR-GARCH | 0.086 | 0.820 | 0.108 |
| FPT | AR-Skewt | 0.126 | 0.822 | 0.054 |
| VN-Index | EGARCH | 0.268 | 0.949 | -0.071 |

---

## 🔑 Key Findings

- ✅ **Historical Beta** is effectively static — adding new observations changes beta by only ~0.01–0.14%, making it unreliable in volatile markets
- ✅ **Rolling Beta** responds more accurately to recent market conditions — quarterly beta for HPG ranged from **0.51 to 1.27** in 2022 alone
- ✅ **Dynamic Conditional Beta** (GARCH-based) is the most sensitive to market volatility regime shifts, outperforming both methods during high-volatility periods
- ✅ Both Rolling Beta and Dynamic Conditional Beta are recommended over Historical Beta when markets exhibit abnormal volatility

---

## 💡 Recommendations

| Market Condition | Recommended Method |
|---|---|
| Sideways / low volatility | Rolling Beta |
| High volatility / crisis periods | Dynamic Conditional Beta |
| General long-term analysis | Historical Beta (baseline only) |

---

## 🛠️ Tools & Libraries

```python
Python · Pandas · NumPy · statsmodels · arch · matplotlib
```

---

## 👥 Authors
**La Phu Hao**, Nguyen Ngoc Huy, Trinh Thi My Linh, Nguyen Tuan Khai, Luong Thi Truc Giang

Ho Chi Minh University of Banking · Supervised by PhD Ha Binh Minh & MSc Nguyen Hoang An

[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?logo=linkedin)](https://linkedin.com/in/laphuhao)
