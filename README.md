# ETF Holdings Inference (Work in Progress)

This project tests whether you can infer an ETF’s **top holdings** using only public data and a simple machine-learning model.

## Data Sources
- **iShares product screener** (ETF universe + metadata)  
- **iShares holdings CSV** (full ETF constituents)  
- **Yahoo Finance** via `yfinance` (ETF + security price history)

## Pipeline Overview
1. Select U.S.-listed **equity ETFs**
2. Download and clean ETF **holdings**
3. Compute **ETF-level features**  
   - annualized return, volatility, Sharpe  
4. Compute **security-level features**  
   - annualized return, volatility, Sharpe  
5. Merge all features into a single modeling dataset
6. Train a logistic regression model to estimate:  
   **P(security is in ETF’s top-25 holdings)**

## Results
- **ROC-AUC:** ~0.83  
- **Log Loss:** ~0.51  
- **Accuracy:** ~0.81  

The model does capture meaningful structural signals in ETF construction and can reliably distinguish higher-weight holdings using only public return data.

However, it cannot replicate portfolio-manager intent, sector rules, or fundamentals, so its predictions are useful for analytics demonstrations but not full holdings inference.

## Notes
- This is an **analytics demo**, not an investment tool.  
- No fundamentals or proprietary datasets are used.  
- Results should not be interpreted as financial advice.
