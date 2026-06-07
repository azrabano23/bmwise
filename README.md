# BMWise — multi-method forecasting, portfolio optimization, and trading simulation

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/)

BMWise is a quantitative finance toolkit that takes a stock's price history and runs the full pipeline a quant analyst would: it **forecasts** future prices with three different model families, **optimizes** a portfolio around the forecast, and **backtests** a trading strategy on the result. Built around BMW and comparable automotive equities, where the volatility makes the modelling choices actually matter.

---

## The problem

Retail investors mostly decide on intuition and lagging indicators, and it shows: **the average individual investor underperforms the market over a 10-year horizon** ([Dalbar Inc., 2023 QAIB](https://www.dalbar.com/)). The gap isn't usually stock-picking talent — it's the absence of *discipline and tooling*: no systematic forecast, no risk-aware position sizing, no way to test a strategy before risking money on it. BMWise is a small, transparent version of the infrastructure that professional desks take for granted.

## Market

This is the consumer edge of a large industry: algorithmic trading and robo-advisory together represent **tens of billions of USD and double-digit growth** (multiple sector analyses put robo-advisory AUM alone in the trillions by the late 2020s). The professional tier is locked up by Bloomberg terminals and hedge-fund infrastructure; the opportunity at the retail/education tier is *legible* tooling — models a user can actually inspect and learn from, rather than a black-box "buy signal." BMWise is built to be read, not just run.

## What it does

1. **Forecasts** the closing price with three model families, so they can be compared rather than trusted blindly.
2. **Optimizes a portfolio** on the modern-portfolio-theory efficient frontier (max-Sharpe weights).
3. **Backtests a trading rule** driven by the forecast, tracking a simulated portfolio's cash and positions day by day.

## Technical breakdown (the core)

Three forecasting paradigms on the same series, plus optimization and a backtest — chosen so the project demonstrates breadth across classical stats and deep learning:

- **Linear Regression** — a transparent baseline; if a fancier model can't beat the trend line, it isn't earning its complexity.
- **ARIMA(5,1,0)** (`statsmodels`) — the classical time-series workhorse: autoregression on a differenced (stationary) series, the right first move for univariate price data.
- **LSTM** (`tensorflow.keras`) — a two-layer, 50-unit recurrent network trained on scaled windowed sequences (Adam, MSE), capturing nonlinear temporal structure the linear models can't.
- **Portfolio optimization** (`PyPortfolioOpt`) — computes efficient-frontier weights and reports expected return / volatility / Sharpe, turning a forecast into a *position* rather than just a prediction.
- **Trading backtest** — a forecast-driven buy/sell rule simulated over the holdout period, tracking cash and share positions so the strategy's behavior is measurable, not asserted.

**Skills demonstrated:** the three dominant forecasting paradigms (regression / ARIMA / LSTM) implemented and compared on real market data; MPT portfolio optimization; building a backtest loop; and the data-engineering around it (scaling, windowing, train/test splitting) with `pandas` / `numpy` / `scikit-learn`.

## Honest scope

This is a research and learning tool, **not investment advice**, and the point is the methodology, not a magic return number — forecasting equity prices is hard and these are standard, interpretable models rather than a proprietary edge. The right way to read the output is "here is how three model families disagree about this stock, and here is what a disciplined strategy on top of them would have done," which is exactly the literacy most retail investors lack.

## Run it

```bash
pip install -r requirements.txt        # pandas, numpy, scikit-learn, statsmodels, tensorflow, PyPortfolioOpt
python bmw.py                          # forecasts + portfolio optimization + backtest
python api.py                          # serve it behind an API
```

## License

MIT — see [LICENSE](LICENSE). Author: **Azra Bano**.
