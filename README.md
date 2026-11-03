# Quantitative Research Portfolio

**Author:** Silam Shrestha · [LinkedIn](https://www.linkedin.com/in/silam-shrestha-a25701394)

Five Python projects on systematic trading, risk and pricing, tested on Japanese market data where data is used. Each notebook explains the idea, the maths, the code, the results and the limitations. Results are reported honestly, including negative ones.

| # | Project | What it shows | Notebook |
|---|---|---|---|
| 1 | Momentum vs Short-Term Reversal | Signal research, long-short portfolios, transaction costs, in-sample vs out-of-sample testing | `01_Momentum_vs_Reversal.ipynb` |
| 2 | Volatility Targeting | Realised volatility, dynamic position sizing, drawdown control, robustness checks | `02_Volatility_Targeting.ipynb` |
| 3 | Pairs Trading with Cointegration | Engle-Granger test, hedge ratios, z-score signals, out-of-sample trading | `03_Pairs_Trading.ipynb` |
| 4 | Black-Scholes Options Pricing | Pricing from first principles, Greeks, Monte Carlo and finite-difference checks, implied volatility | `04_Options_Pricing_Black_Scholes.ipynb` |
| 5 | Market-Making Simulator | Bid-ask quoting, random order arrival, inventory risk and skewing | `05_Market_Making_Simulator.ipynb` |

## Key findings (real Japanese market data)
| Project | Result |
|---|---|
| Momentum vs Reversal | No momentum edge in Japanese large caps (out-of-sample Sharpe 0.01). Reversal looked significant in-sample (gross t = 2.31) but faded out of sample (net Sharpe 0.08); its high turnover made it very cost-sensitive. |
| Volatility Targeting | Cut volatility from 19.9% to 11.3% and max drawdown from −32.7% to −20.3%, but did not improve Sharpe (0.57 vs 0.67). Found and removed an unadjusted ETF split that created a false −90% day. |
| Pairs Trading | No same-industry pair was cointegrated at 5% in 2015–2019; out-of-sample results were small and mostly negative. Fixed a stop-loss re-entry bug that had inflated losses. |
| Black-Scholes | Prices and Greeks confirmed by put-call parity, Monte Carlo (8.4351 vs 8.4333) and finite differences. |
| Market Making | A small inventory skew cut PnL volatility by about 83% with similar average profit. |

## Principles used throughout
- **No look-ahead bias:** every decision uses only information available at that time.
- **Out-of-sample testing:** methods are chosen on one period and tested on a later one.
- **Costs included:** trading costs are subtracted, with sensitivity checks.
- **Limitations stated:** survivorship bias, small samples, simplified costs and multiple testing are discussed.

## How to run
Open any notebook in Google Colab and choose Runtime → Run all.

## Tools
Python · pandas · NumPy · SciPy · statsmodels · Matplotlib · yfinance
