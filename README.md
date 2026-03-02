
# 🚀 AI Quant Trading Platform

Real-time AI-powered stock analysis dashboard with machine learning, reinforcement learning, and Gemini AI — built with Streamlit.


📸 Overview
This platform provides institutional-grade trading insights in a web browser. It combines live market data, a custom Transformer model, RL agent, flash crash detection, portfolio optimization, and Google Gemini AI — all auto-refreshing in real time.

✨ Features
ModuleDescription📡 Live DataAuto-refreshing 1-min intraday bars via Yahoo Finance (5–60s intervals)📊 Technical IndicatorsRSI, MACD, VWAP, rolling volatility, volume spike detection🤖 Transformer ModelCustom PyTorch model trained live — generates BUY / SELL / HOLD signals💥 Flash Crash Detector0–100 risk score across return, volatility, volume, and VWAP dimensions📈 BacktestingSharpe Ratio, Max Drawdown, interactive equity curve (Plotly)🔍 Multi-Stock ScannerScans AAPL, MSFT, GOOGL, AMZN, TSLA simultaneously⚖️ Portfolio OptimizerRisk parity weighting via inverse volatility🎮 RL AgentPPO agent (Stable-Baselines3) with custom Gymnasium environment🧠 Gemini AINatural-language market commentary via Google Gemini API

🛠️ Installation
Prerequisites

Python 3.9+
pip
Google Gemini API key (optional — for AI Decision panel)

Steps
1. Clone the repository
bashgit clone https://github.com/your-username/ai-quant-trading-platform.git
cd ai-quant-trading-platform
2. Install dependencies
bashpip install streamlit streamlit-autorefresh numpy pandas yfinance ta torch plotly gymnasium stable-baselines3 google-generativeai python-dotenv
3. Set up environment variables
bash# Create a .env file in the project root
echo "GEMINI_API_KEY=your_api_key_here" > .env
4. Run the app
bashstreamlit run App.py
```

---

## ⚙️ Configuration

| Parameter | Default | Description |
|---|---|---|
| `GEMINI_API_KEY` | — | Gemini API key in `.env`. AI panel disabled without it. |
| Refresh Interval | 15s | Sidebar slider (5–60 seconds) |
| Selected Stock | AAPL | Dropdown — drives all models and charts |

---

## 🏗️ Architecture
```
App.py
├── get_data()          # Cached yfinance fetcher + indicator pipeline
├── TransformerModel    # PyTorch Transformer — live price prediction
├── flash_crash()       # Heuristic crash risk scorer (0–100)
├── backtest()          # Sharpe ratio + max drawdown + equity curve
├── TradingEnv          # Custom Gymnasium env for RL training
├── risk_parity()       # Inverse-volatility portfolio weights
├── scanner()           # Multi-ticker batch scanner
└── Gemini AI panel     # Google Gemini natural-language analysis
```

---

## 🚀 Usage

1. Select a stock ticker from the dropdown
2. Watch prices, signals, and crash risk auto-refresh live
3. Review the **Price & Prediction** chart for model output
4. Check the **Scanner** table to compare risk across all tickers
5. See **Portfolio Optimizer** for risk-parity suggested weights
6. Hit **Train RL Agent** to train a PPO agent on current data
7. Hit **Generate AI Decision** for Gemini-powered market commentary

---

## 📦 Dependencies
```
streamlit
streamlit-autorefresh
numpy
pandas
yfinance
ta
torch
plotly
gymnasium
stable-baselines3
google-generativeai
python-dotenv

⚠️ Disclaimer
This platform is for educational and research purposes only. It does not constitute financial advice. Ensure compliance with the terms of service of all third-party providers (Yahoo Finance, Google Gemini) before deploying in production.
