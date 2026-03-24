# FX-Regime-Engine
# 📊 Volatility Regime Engine  
*A systematic framework for identifying high- and low-probability trading environments using volatility dynamics*

---

## 1. Overview

This project implements a **volatility regime classification engine** designed to improve trading performance by dynamically adjusting exposure based on market conditions.

The model was developed after observing that:

- **Drawdowns** in my EUR/USD strategy occurred during **low-volatility expansions**
- **Underperformance in gold (XAU/USD)** coincided with **strong directional momentum regimes**

The objective is to:

> **Classify market environments into actionable regimes and integrate them into position sizing and trade filtering.**

---

## 2. Key Features

- 📈 Multi-asset support (EUR/USD, Gold)
- 📉 Rolling volatility computation (20-day baseline)
- 🧠 Regime classification framework (Good / Mixed / Strong / Poor)
- ⚙️ Position sizing overlay based on regime probability
- 📊 Visualization of price vs volatility regimes
- 🔍 Designed for live trading integration

---

## 3. Methodology

### 3.1 Volatility Measurement

- Uses **rolling realized volatility (20-day window)**
- Annualized using:
