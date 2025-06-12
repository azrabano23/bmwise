# BMWise

Retail investors often rely on intuition or basic tools when making decisions about stock investments, leading to suboptimal results. There is a need for a data-driven system that can intelligently forecast stock prices, optimize portfolios, and simulate trading strategies using modern machine learning and financial modeling techniques. This is especially valuable for high-performance automobile stocks like BMW, where market trends can be volatile and complex to navigate.

BMWise is a full-stack financial analysis tool that combines machine learning, time series forecasting, and quantitative finance to analyze, predict, and optimize investment decisions for BMW and similar automotive stocks.

 "Over 90% of individual investors underperform the market over a 10-year period."
— Source: Dalbar Inc., 2023 QAIB Report (Quantitative Analysis of Investor Behavior)

Why This Matters for BMWise:
This statistic highlights a critical gap: most retail investors lack the tools or discipline to outperform even basic index funds. BMWise addresses this issue by automating:

- Data-driven forecasting
- Portfolio optimization
- Objective trading simulation

It replaces guesswork with statistical modeling and machine learning, giving investors a better chance at consistent, risk-adjusted returns — especially in niche sectors like luxury automotive stocks.

# What the Program Does:

Data Loading and Preprocessing:

- Loads historical stock or price data.
- Creates rolling averages (50-day and 200-day moving averages) and lag features to capture historical trends.
- Scales the data to enhance machine learning model performance.

Forecasting:
- Linear Regression: Predicts close prices based on historical data and technical indicators.
- ARIMA: Forecasts time series data using statistical properties of the dataset.
- LSTM: Implements a neural network for advanced time series forecasting.

Portfolio Optimization:
- Calculates mean returns and covariance matrices of stock returns.
- Uses the Efficient Frontier to allocate resources optimally, maximizing risk-adjusted returns.

Algorithmic Trading Simulator:
- Simulates buy-and-sell decisions based on predicted prices.
- Tracks portfolio growth over time based on an initial cash investment.

Backtesting and Performance Analysis:
- Measures strategy performance using metrics like Mean Squared Error (MSE) for regression models.
- Outputs portfolio performance, including Sharpe ratio and volatility.


# Technical Skills Used:

Programming Language: Python

Machine Learning & Deep Learning:
- Scikit-Learn: For linear regression and model evaluation.
- TensorFlow/Keras: To build and train LSTM models for time series forecasting.
- Statsmodels: For implementing ARIMA, a statistical forecasting technique.

Data Manipulation & Analysis:
- Pandas: For dataset loading, preprocessing, and manipulation.
- NumPy: For efficient numerical computations.

Financial Modeling:
- PyPortfolioOpt: For portfolio optimization using risk-return metrics like the Sharpe ratio.
- Statistical calculations for returns and covariances to inform efficient frontier modeling.

Development Tools:
- Google Colab: Ideal for training models with GPU acceleration.

# Libraries for Scaling:
- Scikit-Learn's MinMaxScaler: Used to normalize data for better performance with machine learning models.
- Time Series Analysis: Implementation of rolling averages and lag features for feature engineering.
- ARIMA modeling for forecasting trends in close prices.
