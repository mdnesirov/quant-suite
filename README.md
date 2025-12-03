# 🚀 Quant Suite

> Production-grade quantitative finance system with factor engine, backtesting, portfolio optimization, and automated data pipelines

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status: In Development](https://img.shields.io/badge/status-in%20development-orange.svg)](https://github.com/mdnesirov/quant-suite)

## 📋 Overview

Quant Suite is a comprehensive quantitative finance platform designed for factor-based investing, portfolio optimization, and systematic trading strategies. Built for scalability and production use.

### 🎯 Key Features

- **5 Core Factor Models**: Value, Momentum, Quality, Size, and Low Volatility
- **Backtesting Engine**: Test strategies with realistic transaction costs
- **Portfolio Optimization**: Efficient frontier, max Sharpe, min variance
- **Automated Data Pipeline**: Daily updates with MongoDB storage
- **Interactive Dashboard**: Streamlit-based analytics interface
- **RESTful API**: Access factor data and signals programmatically
- **ML Predictions**: Random Forest, Gradient Boosting, and LSTM models

## 🏗️ Project Structure

```
quant-suite/
│
├── data/                  # Raw and processed data
│   ├── raw/
│   └── processed/
│
├── notebooks/            # Jupyter notebooks for analysis
│   ├── exploration.ipynb
│   └── factor_analysis.ipynb
│
├── factors/              # Factor computation modules
│   ├── __init__.py
│   ├── value.py         # P/B, P/E, EV/EBITDA
│   ├── momentum.py      # 12-1 month returns
│   ├── quality.py       # ROE, margins, debt ratios
│   ├── size.py          # Market cap factors
│   └── volatility.py    # Standard deviation
│
├── backtesting/          # Strategy backtesting
│   ├── __init__.py
│   ├── returns.py
│   ├── transaction_costs.py
│   └── execution.py
│
├── portfolio/            # Portfolio optimization
│   ├── __init__.py
│   ├── optimizer.py
│   └── risk_models.py
│
├── dashboard/            # Streamlit dashboard
│   ├── app.py
│   ├── pages/
│   └── components/
│
├── api/                  # FastAPI endpoints
│   ├── main.py
│   └── routes/
│
├── utils/                # Utility functions
│   ├── __init__.py
│   ├── data_fetcher.py
│   └── db_manager.py
│
├── tests/                # Unit tests
│   └── test_factors.py
│
├── requirements.txt      # Python dependencies
├── .env.example         # Environment variables template
└── README.md            # This file
```

## 🚦 Quick Start

### Prerequisites

- Python 3.8 or higher
- MongoDB Atlas account (free tier)
- Git installed

### Installation

```bash
# Clone the repository
git clone https://github.com/mdnesirov/quant-suite.git
cd quant-suite

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your API keys and database credentials
```

### First Run

```python
# Fetch initial data
python utils/data_fetcher.py

# Compute factors for S&P 500
python factors/compute_all.py

# Run backtests
python backtesting/run_strategies.py

# Launch dashboard
streamlit run dashboard/app.py
```

## 📊 Factor Models

### 1. Value Factor
- **P/B Ratio**: Price-to-Book
- **P/E Ratio**: Price-to-Earnings  
- **EV/EBITDA**: Enterprise Value to EBITDA

### 2. Momentum Factor
- **12-1 Month Returns**: Trailing 12 months excluding most recent month

### 3. Quality Factor
- **ROE**: Return on Equity
- **Profit Margins**: Operating and net margins
- **Debt/Equity**: Financial leverage ratios

### 4. Size Factor
- **Market Capitalization**: Small vs large cap premium

### 5. Low Volatility Factor
- **Standard Deviation**: Daily returns volatility

## 🔬 Backtesting Strategies

- **Top Decile Momentum**: Long top 10% momentum stocks
- **Value Quintile**: Long top 20% value stocks
- **Multi-Factor**: Equal-weighted combination
- **Long-Short**: Long top 10%, short bottom 10%

### Performance Metrics

- Cumulative Returns
- Sharpe Ratio
- Sortino Ratio
- Maximum Drawdown
- Annualized Volatility
- Portfolio Turnover

## 🎨 Dashboard Features

### Pages

1. **Market Overview**: Indices, heatmaps, VIX tracking
2. **Factor Analytics**: Rankings, correlations, performance
3. **Strategy Backtests**: Interactive parameter selection
4. **Portfolio Optimizer**: Efficient frontier visualization
5. **ML Predictions**: Model outputs and forecasts

## 🤖 API Endpoints

```
GET  /api/v1/factors/{ticker}          # Get factor scores for ticker
GET  /api/v1/strategy?factor=value     # Get strategy signals
POST /api/v1/backtest                  # Run custom backtest
GET  /api/v1/portfolio/optimize        # Get optimal portfolio weights
```

## 🔄 Automated Updates

- **Daily**: Price data refresh via GitHub Actions
- **Daily**: Factor recomputation
- **Weekly**: Performance reports (PDF)
- **Monthly**: Model retraining

## 📈 Technology Stack

- **Data**: yfinance, Alpha Vantage, Polygon.io
- **Processing**: Pandas, NumPy
- **Database**: MongoDB Atlas
- **Visualization**: Matplotlib, Seaborn, Plotly
- **Dashboard**: Streamlit
- **API**: FastAPI
- **ML**: Scikit-learn, XGBoost, TensorFlow
- **Deployment**: Vercel (frontend), Render (backend)

## 📝 Development Roadmap

### Phase 1: Foundation (Week 1) ✅
- [x] Project structure
- [x] Data fetching
- [x] Factor computation
- [x] MongoDB integration

### Phase 2: Backtesting (Week 2-3) 🚧
- [ ] Returns calculation
- [ ] Transaction costs
- [ ] Strategy execution
- [ ] Performance metrics

### Phase 3: Dashboard (Week 4) 📅
- [ ] Streamlit setup
- [ ] Factor analytics page
- [ ] Backtest visualization
- [ ] Portfolio optimizer

### Phase 4: Production (Month 2-3) 📅
- [ ] REST API
- [ ] GitHub Actions automation
- [ ] PDF report generation
- [ ] Cloud deployment
- [ ] ML model integration

## 🧪 Testing

```bash
# Run all tests
pytest tests/

# Run with coverage
pytest --cov=. tests/
```

## 📚 Documentation

Detailed documentation available in `/docs`:
- [Factor Methodology](docs/factors.md)
- [Backtesting Guide](docs/backtesting.md)
- [API Reference](docs/api.md)
- [Deployment Guide](docs/deployment.md)

## 🤝 Contributing

Contributions welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

## 📄 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file.

## 🙏 Acknowledgments

- Factor models based on Fama-French research
- Data provided by yfinance and Alpha Vantage
- Inspired by quantitative finance best practices

## 📧 Contact

Made with 💙 by [Murad Nasirov](https://github.com/mdnesirov)

**For wealth management roles and quantitative analysis opportunities**

---

⭐ Star this repo if you find it useful!
