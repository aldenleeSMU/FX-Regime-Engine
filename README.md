# Volatility Regime Engine  
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

-  Multi-asset support (EUR/USD, Gold)
-  Rolling volatility computation (20-day baseline)
-  Regime classification framework (Good / Mixed / Strong / Poor)
-  Position sizing overlay based on regime probability
-  Visualization of price vs volatility regimes
-  Designed for live trading integration

---

## 3. Methodology

### 3.1 Volatility Measurement

- Uses **rolling realized volatility (20-day window)**
- Annualized using: σ_annual = σ_rolling × √252
- Volatility serves as a proxy for:
  - Market participation
  - Liquidity conditions
  - Expansion vs contraction phases

---

### 3.2 Regime Classification Logic

The engine classifies each period into **four regimes**:

| Regime | Interpretation | Trading Implication |
|--------|---------------|--------------------|
| Good   | Favorable volatility + structure alignment | Full risk allocation |
| Mixed  | Unclear conditions | Reduced exposure |
| Strong | Extreme momentum / instability | Selective participation |
| Poor   | Low-quality environment | Minimal or no trading |

---

### 3.3 Asset-Specific Adjustments

The model accounts for **instrument-specific behavior**:

#### EUR/USD (mean-reverting, liquidity-driven)
- Performs best in **moderate volatility**
- Struggles in **low-volatility expansion**

#### XAU/USD (momentum-driven)
- Performs best in **controlled trends**
- Underperforms in **aggressive directional moves**

---

### 3.4 Position Sizing Overlay

Regimes are translated into **risk multipliers**:

#### EUR/USD
- Good → 1.00x  
- Mixed → 0.50x  
- Strong → 0.90x  
- Poor → 0.20x  

#### XAU/USD
- Good → 1.00x  
- Mixed → 0.85x  
- Strong → 0.25x  
- Poor → 0.15x  

This enables:
- Dynamic capital allocation  
- Drawdown control during adverse regimes  
- Maximizing exposure in high-probability environments  

---

## 4. Data

- Source: User-provided CSV (Dukascopy / JForex / broker exports)
- Frequency: Flexible (tested on intraday + daily aggregation)

### Required Fields:
- Timestamp  
- Price (Close / Mid)

---

## 5. Output & Visualization

The engine produces:

-  Price charts with regime overlays  
-  Volatility time series  
-  Highlighted low-probability environments  
-  Cross-asset comparisons  

These outputs are used to:
- Diagnose historical drawdowns  
- Validate regime assumptions  
- Inform live execution decisions  

---

## 6. Practical Application (Live Trading)

This engine is used as a **pre-trade filter and risk management overlay**.

### Workflow:

1. Identify current regime  
2. Adjust:
   - Position size  
   - Trade frequency  
3. Avoid trading during:
   - Poor regimes  
   - Known drawdown environments  

---

## 7. Results & Insights

Key findings from implementation:

- Drawdowns cluster in **misaligned volatility regimes**  
- Filtering or resizing trades:
  - Improves **risk-adjusted returns**
  - Reduces **maximum drawdown**  
- Regime-based sizing outperforms static risk models  

---

## 8. Extensions & Future Work

- Hidden Markov Models (HMM) for probabilistic regimes  
- Integration of:
  - VIX / macro volatility indicators  
  - Liquidity metrics (spread, tick activity)  
- Deployment into **Streamlit dashboard for live monitoring**  

---

## 9. Skills Demonstrated

- Quantitative Research & Strategy Development  
- Time Series Analysis & Volatility Modeling  
- Python (pandas, numpy, matplotlib)  
- Risk Management & Position Sizing  
- Systematic Trading Framework Design  

---

## 10. Author

**Alden Lee**  
FX Trader | Quantitative Strategy Developer  

- Focus: EUR/USD & Gold  
- Approach: Macro-informed, rule-based discretionary trading  
- Objective: Build institutional-grade trading systems and risk frameworks  

---

## 📌 Notes

Developed as part of systematic trading research to enhance **risk-adjusted returns in discretionary FX trading**.


