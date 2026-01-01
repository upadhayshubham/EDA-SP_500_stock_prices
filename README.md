# 📊 Financial Data Analysis & Machine Learning Projects

A collection of data analysis and machine learning projects focused on financial markets, developed as part of my ML bootcamp journey. This repository demonstrates various EDA techniques, statistical analysis, and predictive modeling on real-world financial datasets.

## 🎯 Project Overview

This repository contains multiple exploratory data analysis (EDA) projects and machine learning experiments on financial market data, including stock prices, ETFs, and market indicators. Each analysis applies data science techniques to extract insights and identify patterns in financial time series data.

## 📁 Repository Structure
```
.
├── notebooks/
│   ├── 01_spy_golden_cross_analysis.ipynb
│   ├── 02_market_sentiment_analysis.ipynb
│   └── 03_portfolio_optimization.ipynb
├── data/
│   ├── raw/
│   └── processed/
├── src/
│   ├── data_processing.py
│   └── visualization.py
├── docs/
│   └── financial_terms_glossary.md
├── requirements.txt
├── .python-version
├── .gitignore
└── README.md
```

## ✨ Features & Analyses

### 1. 📈 Golden Cross Detector (SPY Analysis)

Identifies bullish market signals by detecting Golden Cross patterns in SPY (S&P 500 ETF) data.

**Key Features:**
- Calculates 50-day and 200-day moving averages
- Detects Golden Cross crossover points

**Technologies:** pandas

[📓 View Notebook](notebooks/01_spy_golden_cross_analysis.ipynb)

### 2. 📊 Market Sentiment Analysis

*(Coming Soon)* Analysis of market sentiment using news data and social media metrics.

### 3. 💼 Portfolio Optimization

*(Coming Soon)* Portfolio construction and optimization using modern portfolio theory.

### 4. 🔍 Stock Price Prediction

*(Coming Soon)* Time series forecasting using LSTM/ARIMA models.

## 🛠️ Technologies Used

**Core Libraries:**
- **Python 3.13.5**
- **pandas** - Data manipulation and analysis

**Development Tools:**
- **Jupyter Notebook** - Interactive analysis
- **Git** - Version control

## 📦 Installation

### Prerequisites

- Python 3.13 or higher
- pip package manager
- Git

### Setup
```bash
# Clone the repository
git clone https://github.com/upadhayshubham/EDA-SP_500_stock_prices.git
cd EDA-SP_500_stock_prices

# Create virtual environment
python -m venv venv

# Activate virtual environment
# macOS/Linux:
source venv/bin/activate
# Windows:
venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook
```

## 🚀 Quick Start

### Running the Golden Cross Analysis
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Load SPY data
spy_df = pd.read_csv('data/raw/SPY_close_price_5Y.csv')

# Calculate moving averages
spy_df = spy_df.assign(
    ma_50 = lambda d: d['Close'].rolling(window=50, min_periods=50).mean(),
    ma_200 = lambda d: d['Close'].rolling(window=200, min_periods=200).mean(),
    golden_cross = lambda d: ((d['ma_50'] > d['ma_200']) & 
                              (d['ma_50'].shift(1) <= d['ma_200'].shift(1))).astype(int)
)

# Find Golden Cross dates
golden_crosses = spy_df[spy_df['golden_cross'] == 1]
print(golden_crosses[['Date', 'Close', 'ma_50', 'ma_200']])
```

## 📚 Financial Terms Glossary

### Key Concepts Used in This Project

**SPDR S&P 500 ETF Trust (SPY)**
- **ETF**: Exchange-Traded Fund - a basket of stocks traded as a single security
- **SPY**: Ticker for the largest S&P 500 ETF
- **Purpose**: Tracks the S&P 500 index performance

**Moving Averages**
- **50-Day MA**: Short-term trend indicator
- **200-Day MA**: Long-term trend indicator
- **Golden Cross**: When 50-day MA crosses above 200-day MA (bullish signal)

**Market Terms**
- **Bull Market**: Extended period of rising prices
- **Trading Days**: Market open days (~252 per year)
- **Closing Price**: Final trading price at 4:00 PM ET

[📖 Full Glossary](docs/financial_terms_glossary.md)

## 📊 Sample Outputs

### Golden Cross Detection Results

| Date       | Close   | MA_50   | MA_200  | gc     |
|------------|---------|---------|---------|--------|
| 2023-01-15 | 398.50  | 385.20  | 380.15  | ❌     |
| 2023-01-16 | 402.30  | 386.45  | 380.22  | ✅     |
| 2023-01-17 | 405.10  | 387.80  | 380.30  | ❌     |

## 📈 Project Roadmap

- [x] Golden Cross detector implementation
- [x] Moving average calculations
- [ ] Basic data visualization
- [ ] Add Death Cross detection (bearish signal)
- [ ] Implement backtesting framework
- [ ] Add more technical indicators (RSI, MACD, Bollinger Bands)
- [ ] Market sentiment analysis from news
- [ ] Portfolio optimization module
- [ ] Machine learning price prediction models
- [ ] Real-time data streaming integration

## 🤝 Contributing

This is a personal learning project, but suggestions and feedback are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## 🎓 Learning Resources

**References:**
- [Pandas Official ](https://pandas.pydata.org/)

## 🙏 Acknowledgments

- **Python Data Science Community** - For excellent libraries and documentation

## 📧 Contact

**Shubham** - Senior Java Developer & ML Enthusiast

- GitHub: [@upadhayshubham](https://github.com/upadhayshubham)
- LinkedIn: [Shubham Upadhay](https://www.linkedin.com/in/shubham-upadhyay-b36b7321b/)
- Email: mailmeshubhamsomu@gmail.com

## 🔖 Tags

`#python` `#data-science` `#machine-learning` `#finance` `#stock-analysis` `#pandas` `#jupyter` `#technical-analysis` `#algorithmic-trading` `#portfolio-management`

---

⭐ **Star this repository** if you found it helpful for your learning journey!

💡 **Fork it** to create your own financial analysis projects!

📚 **Follow along** as I continue building more ML/data science projects!