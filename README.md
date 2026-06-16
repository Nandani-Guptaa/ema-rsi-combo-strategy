# EMA Crossover + RSI Filter Strategy
### Algorithmic Trading Research | EUR/USD Forex | Python

A systematic long-only trading strategy combining **EMA crossover signals** with an **RSI confirmation filter** on EUR/USD daily data. Backtested over 5 years to evaluate risk-adjusted performance against a Buy & Hold benchmark.

---

## 📌 Strategy Logic

| Component | Parameter |
|---|---|
| Asset | EUR/USD (`EURUSD=X`) |
| Timeframe | Daily (1D) |
| Data Period | 5 Years |
| Fast EMA | 9 |
| Slow EMA | 21 |
| RSI Length | 14 |
| RSI Overbought | 70 |
| RSI Oversold | 30 |

**Entry Signal:** EMA(9) crosses above EMA(21) AND RSI < 70 (not overbought)

**Exit Signal:** EMA(9) crosses below EMA(21) AND RSI > 30 (not oversold)

The RSI filter acts as a **noise reducer** — preventing entries in overextended price conditions where crossover signals tend to be false positives.

---

## 📊 Performance Metrics

| Metric | Value |
|---|---|
| Total Return | **+11.11%** |
| Buy & Hold Return | -1.45% |
| Sharpe Ratio | 0.42 |
| Sortino Ratio | 0.51 |
| Max Drawdown | -8.68% |
| Number of Trades | 22 |
| Win Rate | 45.13% |
| Backtest Period | Jul 2021 — Jun 2026 |

> ✅ Strategy outperformed Buy & Hold by **+12.56%** over the 5-year period — profitable during a period where passive EUR/USD exposure was negative.

---

## 📈 Output Visualizations

The notebook generates a 3-panel chart:
- **Panel 1:** EUR/USD price with EMA lines + entry/exit markers
- **Panel 2:** RSI oscillator with overbought/oversold bands
- **Panel 3:** Strategy equity curve vs Buy & Hold benchmark

---

## 🗂️ Repository Structure

```
ema-rsi-combo-strategy/
│
├── ema_rsi_strategy.ipynb     # Main notebook (Google Colab)
├── ema_rsi_strategy.py        # Python script version
├── outputs/
│   └── equity_curve.png       # Sample output chart
└── README.md
```

---

## ▶️ How to Run

**Option 1 — Google Colab (Recommended)**
```
1. Open ema_rsi_strategy.ipynb in Google Colab
2. Runtime → Run All
3. Results printed + charts displayed automatically
```

**Option 2 — Local**
```bash
pip install yfinance pandas pandas_ta numpy matplotlib
python ema_rsi_strategy.py
```

---

## 🔍 Key Research Finding

This strategy represents a **classic risk-return tradeoff** when compared against a plain RSI mean reversion approach:

- The RSI filter **reduces number of trades** significantly
- Tighter entry conditions → **lower drawdown** but potentially **lower total return**
- Sharpe/Sortino ratios reveal whether the risk reduction is worth the return sacrifice

This tradeoff is the core publishable finding being developed into a formal research paper.

---

## 🔗 Related Research

| Strategy | Repository |
|---|---|
| RSI Mean Reversion | *[link to repo]* |
| MA Crossover | *[link to repo]* |
| EMA + RSI Combo *(this repo)* | — |

> Part of an ongoing **Algorithmic Trading Research Series** on EUR/USD Forex market.

---

## 🛠️ Tech Stack

```
Python 3       yfinance       pandas
pandas_ta      numpy          matplotlib
```

---

## 👩‍💻 Author

**Nandani Gupta** — B.Tech CSE (Data Science), PSIT Kanpur

[![LinkedIn](https://img.shields.io/badge/LinkedIn-nandaniiguptaa-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/nandaniiguptaa)
[![GitHub](https://img.shields.io/badge/GitHub-Nandani--Guptaa-black?style=flat&logo=github)](https://github.com/Nandani-Guptaa)
