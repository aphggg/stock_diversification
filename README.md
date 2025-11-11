# Portfolio Clustering & Diversification Analysis

This project explores **stock diversification** using unsupervised learning (K-Means clustering) on S&P 500 stock returns.  
It creates and compares three simple portfolios:

1. **Cluster-based portfolio** - one stock selected from each cluster (diversified by behavior)  
2. **Market portfolio (using proxy stocks from the S&P500)** - equal-weighted portfolio using all stocks in the dataset  
3. **Random portfolio** – equal-weighted random selection of stocks  


---

## Methodology Overview
1. **Data source**  
   - Daily returns of S&P 500 stocks from Yahoo Finance.
2. **Feature engineering**  
   - Normalization (log-returns) and standardization of returns (`Xz`).
3. **Clustering**  
   - K-Means with `best_k` chosen via silhouette analysis.  
4. **Portfolio construction**
   - **Cluster portfolio**: pick one from each cluster.  
   - **Random portfolio**: equal-weight random stocks.  
   - **Market (S&P500 Proxy)**: equal-weight all stocks in the dataset.
5. **Performance evaluation**
   - CAGR, volatility, Sharpe ratio, and maximum drawdown.

---

## Results Snapshot
| Metric | Cluster | SP500 Proxy | Random |
|:--|:--:|:--:|:--:|
| CAGR | ~20% | 18% | 16% |
| Volatility | 18% | 19% | 26% |
| Sharpe | 1.1 | 1.0 | 0.7 |
| Max Drawdown | −19% | -23% | 35% |


