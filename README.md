# Portfolio Clustering & Diversification Analysis

This project explores **data-driven portfolio construction** using unsupervised learning (K-Means clustering) on S&P 500 stock returns.  
It then builds and compares three simple portfolios:

1. **Cluster-based portfolio** – one stock selected from each cluster (diversified by behavior)  
2. **Market portfolio (ALL EW)** – equal-weighted portfolio using all stocks in the dataset  
3. **Random portfolio** – equal-weighted random selection of the same size as the cluster portfolio  

The analysis evaluates returns, risk, and efficiency (Sharpe ratio), and visualizes cumulative wealth curves over time.

---

## Key Concepts
- **Clustering stocks** by similarity in historical return patterns  
- **Portfolio diversification** via uncorrelated groups  
- **Risk metrics**: volatility, drawdown, Sharpe ratio  
- **Visualization**: 2D cluster maps (PCA) and cumulative wealth curves  

---

## Methodology Overview
1. **Data source**  
   - Daily returns of S&P 500 stocks from Yahoo Finance (via `yfinance`).
2. **Feature preparation**  
   - Normalization and standardization of returns (`Xz`).
3. **Clustering**  
   - K-Means with `best_k` chosen via silhouette analysis.  
   - Stocks assigned to clusters stored in `labels2`.
4. **Portfolio construction**
   - **Cluster portfolio**: pick one (or two) from each cluster.  
   - **Random portfolio**: equal-weight N random stocks.  
   - **Market (ALL)**: equal-weight all stocks in the dataset.
5. **Performance evaluation**
   - CAGR, volatility, Sharpe ratio, and maximum drawdown.
6. **Visualization**
   - Plotly scatter (PCA clusters).  
   - Matplotlib cumulative wealth curves comparing the three portfolios.

---

## 🚀 Results Snapshot
| Metric | Cluster | ALL EW | Random |
|:--|:--:|:--:|:--:|
| CAGR | ~20% | 18% | 17% |
| Volatility | 17–18% | 18% | 19% |
| Sharpe | ~1.1 | 1.0 | 0.9 |
| Max Drawdown | −19% | −22% | −25% |

*(Values shown for illustration — recompute with your data.)*

---

## Tools & Libraries
- **Python 3.11**
- `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `plotly`
- (optional) `yfinance`, `scipy`, `openpyxl`

---

## How to Run
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
python -m venv .venv
source .venv/bin/activate  # (Windows: .venv\Scripts\activate)
pip install -r requirements.txt
jupyter lab

