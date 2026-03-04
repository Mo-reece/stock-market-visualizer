# Stock Market Trend Visualizer

**Author:** Okurut Maurice Leonard

An interactive financial analysis tool that pulls two years of daily stock data from Yahoo Finance and renders eight publication-quality Plotly charts — candlesticks, moving averages, correlation heatmaps, volatility surfaces, and more. All charts support hover tooltips, zoom, pan, and range selection out of the box.

![Project Preview](./assets/preview.png)

---

## Overview

Five major tech tickers — AAPL, TSLA, MSFT, GOOGL, AMZN — across a 2-year daily window. The notebook handles data fetching, caching, feature engineering, and chart generation in a single pass. Change the ticker list in one cell and re-run; everything else adapts automatically.

**Tickers:** AAPL · TSLA · MSFT · GOOGL · AMZN
**Period:** 2 years of daily OHLCV data
**Data source:** Yahoo Finance via `yfinance`

---

## Visualizations

| # | Chart | What it shows |
|---|-------|---------------|
| 1 | **Candlestick + Volume** | OHLC candles with color-coded volume bars and range selectors |
| 2 | **Moving Averages** | Price with SMA 20/50/200 overlays and golden/death cross annotations |
| 3 | **Normalized Comparison** | All tickers on a base-100 scale for fair performance comparison |
| 4 | **Returns Distribution** | Overlaid histograms with fitted normal distribution curves |
| 5 | **Rolling Volatility** | 21-day annualized volatility time series per ticker |
| 6 | **Correlation Heatmap** | Pairwise return correlations with annotated values |
| 7 | **Volume Analysis** | Per-ticker volume subplots with 20-day moving average overlays |
| 8 | **Statistics Dashboard** | 4-panel summary: cumulative returns, risk/return scatter, drawdown, Sharpe |

---

## Tech Stack

- **Python 3.9+**
- **yfinance** — Yahoo Finance data fetching with local CSV caching
- **pandas** — time-series manipulation and feature engineering
- **numpy** — numerical computing
- **plotly** — interactive charts (graph_objects + make_subplots)
- **scipy** — distribution fitting for returns analysis

---

## Project Structure

```
stock-market-visualizer/
├── stock_market_visualizer.ipynb   # Main notebook
├── assets/                         # Screenshots / preview images
├── *.csv                           # Cached ticker data (auto-generated)
├── 01_candlestick_AAPL.html
├── 02_moving_averages_AAPL.html
├── 03_normalized_comparison.html
├── 04_returns_distribution.html
├── 05_rolling_volatility.html
├── 06_correlation_heatmap.html
├── 07_volume_analysis.html
├── 08_statistics_dashboard.html
├── requirements.txt
└── README.md
```

---

## Getting Started

```bash
git clone https://github.com/Mo-reece/stock-market-visualizer.git
cd stock-market-visualizer

python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

pip install -r requirements.txt
jupyter notebook stock_market_visualizer.ipynb
```

Run all cells to generate the full analysis and export the interactive HTML charts.

### Analyzing different tickers

Edit the config cell at the top of the notebook:

```python
TICKERS  = ['JPM', 'GS', 'BAC', 'WFC', 'C']   # any valid Yahoo Finance symbols
PERIOD   = '2y'   # 1y | 2y | 5y | 10y | max
INTERVAL = '1d'   # 1d | 1wk | 1mo
```

---

## Financial Metrics

| Metric | Description |
|--------|-------------|
| Daily Returns | Percentage change in adjusted close |
| Log Returns | Natural log of price ratios |
| Cumulative Returns | Total return since period start |
| SMA 20 / 50 / 200 | Simple moving averages |
| EMA 20 | Exponential moving average |
| Rolling Volatility | 21-day annualized std of returns |
| Sharpe Ratio | Annualized return divided by annualized volatility |
| Max Drawdown | Largest peak-to-trough decline |
| Correlation Matrix | Pairwise return correlations |

---

## Roadmap

- [ ] Bollinger Bands and RSI
- [ ] Streamlit dashboard for live exploration
- [ ] Sector comparison mode
- [ ] Markowitz efficient frontier overlay
- [ ] Fundamental data integration (P/E, earnings dates)

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

*Data provided by [Yahoo Finance](https://finance.yahoo.com/) via [yfinance](https://github.com/ranaroussi/yfinance).*
