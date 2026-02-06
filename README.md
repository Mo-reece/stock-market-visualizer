# Stock Market Trend Visualizer: Interactive Multi-Stock Analysis

An interactive stock market analysis tool that fetches real-time data from Yahoo Finance and creates publication-quality interactive visualizations using Plotly. Analyze price trends, volatility, correlations, and technical indicators across multiple stocks.

## Project Overview

This project demonstrates financial data acquisition, time-series analysis, and interactive visualization by analyzing major tech stocks over a 2-year period. All charts are fully interactive with hover tooltips, zoom, pan, and range selection.

**Tickers Analyzed:** AAPL, TSLA, MSFT, GOOGL, AMZN
**Period:** 2 Years of Daily Data
**Portfolio Project:** Day 2 of 30

## Key Features

- Real-time data from Yahoo Finance API with local caching
- 8 interactive Plotly visualizations (hover, zoom, pan)
- Technical indicators: SMA 20/50/200, EMA 20, golden/death cross detection
- Risk metrics: Sharpe ratio, max drawdown, rolling volatility
- Easy customization: change tickers in one line and re-run
- Error handling: graceful failure per ticker, cached data fallback

## Visualizations

| # | Chart | Description |
|---|-------|-------------|
| 1 | **Candlestick + Volume** | OHLC candles with color-coded volume bars and range selectors |
| 2 | **Moving Averages** | Price with SMA 20/50/200 overlays, golden/death cross annotations |
| 3 | **Normalized Comparison** | All stocks on same base-100 scale for fair comparison |
| 4 | **Returns Distribution** | Overlaid histograms with normal distribution curve |
| 5 | **Rolling Volatility** | 21-day annualized volatility time series |
| 6 | **Correlation Heatmap** | Returns correlation matrix with annotated values |
| 7 | **Volume Analysis** | Per-stock volume subplots with 20-day moving average |
| 8 | **Statistics Dashboard** | 4-panel summary: returns, risk/return, drawdown, Sharpe |

## Technical Stack

- **Python 3.9+**
- **yfinance** - Yahoo Finance API for real-time stock data
- **pandas** - Time-series data manipulation and feature engineering
- **numpy** - Numerical computing
- **plotly** - Interactive visualization (graph_objects + subplots)
- **scipy** - Statistical analysis (distribution fitting)

## Project Structure

```
stock-market-visualizer/
├── data/                              # Cached CSV files (auto-generated)
├── notebooks/
│   └── stock_market_visualizer.ipynb  # Main analysis notebook
├── visualizations/                    # Interactive HTML charts (auto-generated)
│   ├── 01_candlestick_AAPL.html
│   ├── 02_moving_averages_AAPL.html
│   ├── 03_normalized_comparison.html
│   ├── 04_returns_distribution.html
│   ├── 05_rolling_volatility.html
│   ├── 06_correlation_heatmap.html
│   ├── 07_volume_analysis.html
│   └── 08_statistics_dashboard.html
├── requirements.txt
└── README.md
```

## Getting Started

### Prerequisites

```bash
# Clone the repository
git clone https://github.com/yourusername/stock-market-visualizer.git
cd stock-market-visualizer

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Running the Analysis

```bash
# Launch Jupyter Notebook
jupyter notebook notebooks/stock_market_visualizer.ipynb
```

Or use Jupyter Lab:
```bash
jupyter lab
```

Run all cells to generate the complete analysis and interactive charts.

### Analyzing Custom Stocks

Open the notebook and modify the configuration in the first code cell:

```python
# Change these to analyze any stocks
TICKERS = ['JPM', 'GS', 'BAC', 'WFC', 'C']  # Example: banking sector
PERIOD = '2y'    # Options: 1y, 2y, 5y, 10y, max
INTERVAL = '1d'  # Options: 1d, 1wk, 1mo
```

Then re-run all cells. The analysis automatically adapts to any valid Yahoo Finance ticker symbols.

## Data Source

**API:** Yahoo Finance via [yfinance](https://github.com/ranaroussi/yfinance) Python library

**Features:**
| Column | Description | Type |
|--------|-------------|------|
| Open | Opening price | Numeric |
| High | Highest price of the day | Numeric |
| Low | Lowest price of the day | Numeric |
| Close | Closing price | Numeric |
| Adj Close | Adjusted closing price (splits/dividends) | Numeric |
| Volume | Number of shares traded | Numeric |

## Financial Metrics Computed

- **Daily Returns** - Percentage change in adjusted close price
- **Log Returns** - Natural log of price ratios (for statistical properties)
- **Cumulative Returns** - Total return since start of period
- **Moving Averages** - SMA 20, 50, 200 and EMA 20
- **Rolling Volatility** - 21-day annualized standard deviation of returns
- **Sharpe Ratio** - Risk-adjusted return (annualized return / annualized volatility)
- **Maximum Drawdown** - Largest peak-to-trough decline
- **Correlation Matrix** - Pairwise return correlations

## Skills Demonstrated

- **API Integration** - Real-time data fetching with error handling and caching
- **Data Engineering** - Time-series preprocessing, feature engineering, multi-stock alignment
- **Interactive Visualization** - 8 publication-quality Plotly charts with tooltips and controls
- **Financial Domain Knowledge** - Technical indicators, risk metrics, portfolio analysis
- **Clean Code** - Modular functions, docstrings, consistent styling, easy customization

## Future Enhancements

- [ ] Add Bollinger Bands and RSI technical indicators
- [ ] Build a Streamlit/Dash interactive dashboard
- [ ] Implement sector comparison analysis
- [ ] Add portfolio optimization (Markowitz efficient frontier)
- [ ] Include fundamental data (P/E ratio, earnings dates)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Financial data provided by [Yahoo Finance](https://finance.yahoo.com/) via [yfinance](https://github.com/ranaroussi/yfinance)
- Inspired by quantitative finance and technical analysis methodologies

---

**Author:** [Your Name]
**Date:** February 2026
**Portfolio:** [yourwebsite.com](https://yourwebsite.com)
**LinkedIn:** [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile)
