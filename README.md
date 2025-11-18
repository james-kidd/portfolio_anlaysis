# ETF Holdings Inference (Work in Progress)

This repo explores whether you can infer an ETF’s top holdings using only **public data** and a simple ML model.

**Data sources / APIs**
- iShares product screener JSON endpoint (universe + metadata)
- iShares holdings `.ajax` CSV endpoints (full ETF holdings)
- Yahoo Finance via `yfinance` (ETF price history → annualized return, vol, Sharpe)

**What the notebook does**
- Builds a small universe of equity ETFs
- Downloads and cleans holdings + ETF-level performance features
- Trains a logistic regression model to estimate  
  _P(security is in ETF’s top-25 holdings)_

**Important**
- Model is **deliberately incomplete**: no fundamentals (market cap, beta, valuations, factors), mixed ETF types, small sample.
- Results are weak and **not** suitable for real investment decisions; this is a **methods / analytics demo**, not a production model.


