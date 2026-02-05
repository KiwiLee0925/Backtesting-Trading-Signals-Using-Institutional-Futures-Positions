# Backtesting-Trading-Signals-Using-Institutional-Futures-Positions
An Empirical Study on TXF Major Institutional Investors (2010–2025)

This project is part of the **EDGE Internship**, focusing on the next step of building a quantitative backtesting framework:  
**designing and evaluating trading signals based on institutional investor behavior** in the Taiwan Index Futures (TXF).

The analysis investigates whether positions held by major institutional investors can be translated into meaningful and robust trading signals across different market regimes.

---

## Data Description

The study uses **Taiwan Index Futures (TXF)** data and position information of the **three major institutional investors**:

- **Foreign Investors**
- **Investment Trusts**
- **Dealers**

Two types of open interest (OI) data are considered:

1. **Net Open Interest by Contracts (Value-based OI)**  
2. **Net Open Interest by Quantity (Position-based OI)**

> For strategy construction, the analysis primarily focuses on **net open interest by quantity**, as it more directly reflects directional positioning and trend behavior.

---

## Sample Periods

The backtest is divided into two regimes:

- **In-sample period:**  
  `2010-01-01 ~ 2019-12-31`

- **Out-of-sample period:**  
  `2020-01-01 ~ 2025-06-30`

A vertical split is applied in all visualizations to highlight structural changes before and after 2020.

---

## Exploratory Analysis

The project first visualizes the time series of net open interest (quantity-based) for:

- Dealers
- Investment Trusts
- Foreign Investors
- Aggregated positions of all three institutions

Key observations from the **in-sample period** include:

- Investment Trusts show **low volatility** and often move **opposite** to Foreign Investors.
- Dealers’ positions are relatively **range-bound**, reflecting hedging and arbitrage behavior.
- Foreign Investors dominate **long-term trends**, and their positions closely resemble the aggregated institutional OI.

These findings are interpreted through the lens of each institution’s **capital size and trading role**.

---

## Strategy Logic

Based on institutional characteristics and observed patterns, the strategy framework is constructed as follows:

1. **Long-term trend strategy**
   - Follow the direction of **Foreign Investors’ net positions**
   - Alternatively, trade **against Investment Trusts** as a contrarian signal

2. **Short-term momentum signal**
   - If Dealers exhibit **abnormally large net buying or selling**, it may indicate strong short-term market momentum worth following

This structure is tested across both sample periods to assess robustness.

---

## In-Sample vs Out-of-Sample Comparison

A regime comparison reveals clear structural shifts after 2020:

- Investment Trusts transitioned from long-term net short to **persistent net long**
- Foreign Investors reduced exposure and turned **more defensive**
- Dealers increased short-term momentum-driven activity
- The aggregated institutional structure shifted from **bullish bias to bearish oscillation**

Despite these changes, the **core strategy logic remains applicable**, provided that signal interpretation is adjusted dynamically.

---

## Macro Interpretation

Major events around 2020 help explain the structural break, including:

- COVID-19 pandemic
- Taiwan presidential election
- Domestic political events
- Rising geopolitical tension affecting foreign capital flows

These factors highlight why institutional signals should be interpreted **within macro and regime context**, rather than mechanically applied.

---

## Tools & Implementation

- **Python** for data processing and visualization
- Time-series plots with regime separation
- Backtesting logic focused on signal interpretation rather than execution optimization

---

## References

- Python notebook (Google Colab):  
  https://colab.research.google.com/drive/1pcG1JF2vN2YP6LPQflQMCtLUss_ATHXZ?usp=sharing

- Major events reference:  
  https://www.upmedia.mg/2020top10/2020top10-taiwan.php

---

## Author

**Chi-Wei Lee**  
Department of Civil Engineering, National Taiwan University  
EDGE Internship Program
