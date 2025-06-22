# Aten Trading Bot

*A GitHub-hosted AI-driven cryptocurrency trading bot*

---

## 🚀 Table of Contents

* [Features](#features)
* [Demo](#demo)
* [Getting Started](#getting-started)

  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
  * [Configuration](#configuration)
* [Usage](#usage)

  * [Backtesting](#backtesting)
  * [Training the Model](#training-the-model)
  * [Live Trading](#live-trading)
* [Project Structure](#project-structure)
* [Strategies & Components](#strategies--components)
* [Logging & Output](#logging--output)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)

---

## ✨ Features

* **Multi-Strategy Engine**: Combines candlestick pattern detection with a Random Forest classifier for signal validation.
* **Exchange Integration**: Supports Kraken Pro (via `ccxt`) for fetching market data and executing orders.
* **Config-Driven**: Manage API keys & thresholds through `config.json`.
* **Backtesting & Simulation**: Evaluate strategies on historical OHLCV.
* **Real-Time Trading**: 24/7 market scanning & automated order execution.
* **Detailed Logging**: Trade history, performance metrics, and error tracking.

---

## 🎬 Demo

*Add your demo GIF or screenshot in `.github/assets/demo.gif` and update this section.*

---

## 🛠️ Getting Started

### Prerequisites

* Python 3.9 or higher
* Git
* (Optional) Docker for containerized deployment

### Installation

```bash
# Clone repository
git clone https://github.com/Akhenaten87/aten-trading-bot.git
cd aten-trading-bot

# Create & activate virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install --upgrade pip
pip install -r requirements.txt
```

### Configuration

1. Copy example config:

   ```bash
   cp config.example.json config.json
   ```
2. Open `config.json` and set your API credentials & trading pairs:

   ```json
   {
     "exchange": "kraken",
     "api_key": "YOUR_API_KEY",
     "api_secret": "YOUR_API_SECRET",
     "trading_pairs": ["BTC/USD", "ETH/USD"],
     "order_size": 0.001,
     "confidence_threshold": 0.6
   }
   ```
3. Update strategy parameters in `strategy_config.json` as needed.

---

## 🎯 Usage

### Backtesting

```bash
python backtest.py \
  --config config.json \
  --strategy strategy_config.json
```

### Training the Model

```bash
python src/model.py \
  --data data/training_data.csv \
  --output models/model.pkl
```

### Live Trading

```bash
python src/live_prediction.py \
  --config config.json \
  --strategy strategy_config.json
```

---

## 📁 Project Structure

```text
aten-trading-bot/
├── .github/                # GitHub workflows & assets (badges, logo, demo gif)
├── config.example.json     # Sample configuration
├── requirements.txt        # Python deps
├── data/                   # Historical OHLCV CSVs
├── models/                 # Trained ML models
├── logs/                   # Logs & trade history
├── src/                    # Source code modules
│   ├── model.py            # ML training script
   ├── live_prediction.py  # Live trading engine
   ├── candlestick_analysis.py
   ├── candlestick_features.py
   ├── signal_generator.py
   └── analyze_patterns.py
├── backtest.py             # Backtesting harness
├── README.md               # This file
└── LICENSE
```

---

## 🧠 Strategies & Components

* **Candlestick Pattern Analysis**: Detects Doji, Hammer, Engulfing patterns in OHLCV data.
* **ML Model**: Random Forest classifier using extracted candlestick & window features.
* **Signal Generation**: Merges pattern signals + ML confidence threshold for buy/sell/hold.

---

## 📊 Logging & Output

* **Logs**: Stored under `logs/` with detailed timestamps & error traces.
* **Trade History**: `logs/trades.csv` for performance review & audit.

---

## 🤝 Contributing

Contributions are welcome! Please follow:

1. Fork repository
2. Create branch: `git checkout -b feature/YourFeature`
3. Commit: `git commit -m "Add feature"`
4. Push: `git push origin feature/YourFeature`
5. Open a Pull Request

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 📬 Contact

Maintainer: **Fareed Akhenaten**
Email: [your.email@example.com](mailto:your.email@example.com)
GitHub: [@Akhenaten87](https://github.com/Akhenaten87)

Happy trading with Aten! \:sun\_with\_face:
