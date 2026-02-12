# Equity and Crypto Market Dynamics Dashboard

An interactive financial analytics dashboard analyzing correlations, betas, and price performance across S&P 500 sectors and cryptocurrencies.

## 🎯 Features

### 📈 Three Interactive Pages

1. **Returns Page** - Normalized price performance across all assets
2. **Correlations Page** - Pearson correlation coefficients relative to SPX
3. **Betas Page** - Systematic risk and volatility measures

### 📊 Data Coverage

- **Period**: December 14, 2025 - February 10, 2026
- **Frequency**: 10-minute intervals
- **Assets Tracked**: 15 total
  - S&P 500 Index (SPX)
  - 11 Sector ETFs (XLK, XLF, XLV, XLC, XLI, XLY, XLP, XLE, XLU, XLRE, XLB)
  - 3 Cryptocurrencies (BTC, ETH, SOL)

### 🎨 Interactive Features

- **Toggle Controls**: Show/hide individual assets on charts
- **Crosshair Hover**: Vertical line tracks your cursor position
- **Color-Coded Assets**: Each asset has a distinct, recognizable color
- **Rolling Time Series**: 100-interval (~2.5 trading days) sliding window for correlations and betas
- **Responsive Design**: Works on desktop, tablet, and mobile

## 📐 Methodology

### Correlation Calculation
- **Metric**: Pearson correlation coefficient
- **Formula**: Measures linear relationship between asset and SPX returns
- **Range**: -1 (perfect negative) to +1 (perfect positive)
- **Data**: 10-minute interval returns over full period

### Beta Calculation
- **Metric**: Beta coefficient (β)
- **Formula**: β = Cov(Asset, SPX) / Var(SPX)
- **Interpretation**: 
  - β = 1: Moves 1:1 with market
  - β > 1: More volatile than market
  - β < 1: Less volatile than market
- **Method**: OLS regression on 10-minute returns

### Rolling Window
- **Size**: 100 intervals (approximately 2.5 trading days)
- **Purpose**: Captures dynamic relationship changes over time
- **Data Points**: 1,293 rolling calculations per asset

## 🛠️ Technology Stack

- **Frontend**: React 18, Chart.js 4.4.0
- **Styling**: Custom CSS with dark theme
- **Fonts**: JetBrains Mono (data), Urbanist (UI)
- **Data**: Embedded JSON (self-contained HTML)
- **Deployment**: GitHub Pages (static hosting)

## 📊 Key Insights from Analysis Period

### Market Overview
- **SPX**: +1.74% (modest gain despite sector divergence)
- **Top Performers**: Energy (+18.85%), Materials (+15.30%), Industrials (+10.35%)
- **Underperformers**: Crypto (-20% to -33%), Tech (-0.32%), Financials (-2.40%)

### Correlation Highlights
- **Highest**: Technology (XLK) 0.849 - moves strongly with market
- **Lowest**: Consumer Staples (XLP) -0.048 - defensive hedge
- **Crypto**: Moderate correlation (0.4-0.5), indicating partial decoupling

### Beta Highlights
- **Highest Volatility**: Ethereum (2.49x), Solana (2.00x), Bitcoin (1.96x)
- **Sector Leader**: Technology (1.62x) - amplifies market moves
- **Most Stable**: Energy (0.32x), Utilities (0.33x), Healthcare (0.33x)

## 🚀 Local Development

This is a self-contained HTML file with all dependencies via CDN. Simply:

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# Open the dashboard
open index.html
# or
python -m http.server 8000  # Then visit http://localhost:8000
```

## 📁 File Structure

```
.
├── index.html          # Main dashboard (1.9MB, all data embedded)
└── README.md          # This file
```

## 🔗 Data Sources

- **Equity Data**: Yahoo Finance API (10-minute OHLCV)
- **Crypto Data**: Yahoo Finance API (10-minute OHLCV, market hours only)
- **Calculations**: Python/Pandas for correlation and beta analysis

## 📝 License

MIT License - feel free to use and modify

## 👤 Author

**Jose Terrazas**

## 🙏 Acknowledgments

Built with Claude (Anthropic) for financial market analysis and visualization.

---

**Note**: This dashboard is for educational and analytical purposes only. Not financial advice.
