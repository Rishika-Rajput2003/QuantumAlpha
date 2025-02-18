# QuantumAlpha: Alpha Generation and Portfolio Backtesting

## Project Overview

**QuantumAlpha** is a quantitative finance project that combines machine learning and finance to generate actionable trading signals (alpha) and optimize portfolio performance. The project uses deep learning models, such as Long Short-Term Memory (LSTM), to predict stock price trends and create portfolios based on these predictions. It also includes a robust backtesting framework to evaluate portfolio performance over time and compare it to a market benchmark (the S&P 500 index).

## Project Flow

The project follows a pipeline structure to generate alpha and evaluate portfolio performance:

1. **Data Acquisition**: Fetch historical stock data for selected tickers (stocks) and benchmark data (S&P 500).
2. **Data Preparation**: Clean and process the stock data, calculate technical indicators, and prepare the data for modeling.
3. **Modeling**: Train a machine learning model, specifically an LSTM (Long Short-Term Memory) model, to predict stock price movements based on historical data and technical indicators.
4. **Alpha Generation**: Use the model's predictions to generate buy, sell, or hold signals for each stock. Portfolio weights are assigned based on these signals.
5. **Portfolio Backtesting**: Simulate the portfolio performance over the historical period using the generated alpha signals. Daily portfolio values are calculated by applying stock price changes and portfolio weights.
6. **Performance Evaluation**: Assess the performance of the portfolio using various financial metrics such as return, Sharpe ratio, maximum drawdown, alpha, and beta.
7. **Visualization**: Plot the portfolio’s performance against the benchmark (S&P 500) to visualize how the strategy would have performed.

## Datasets Used

- **Stock Data**: The project uses historical stock price data for the tickers selected for analysis. This data is fetched from Yahoo Finance using the `yfinance` library. Each stock’s closing price is used to model price movements.

- **Benchmark Data**: The benchmark for portfolio performance comparison is typically the S&P 500 index (symbol: `^GSPC`), which is also fetched from Yahoo Finance. This allows comparison of the portfolio's performance against the broader market to evaluate whether the strategy outperforms the market.

## Model Used

The core machine learning model used for alpha generation is a **Long Short-Term Memory (LSTM)** network, a type of Recurrent Neural Network (RNN) suited for time-series prediction tasks. LSTM is chosen for its ability to learn from sequential data, making it well-suited for predicting stock price trends.

- **LSTM Model**: The model is trained on historical stock price data along with technical indicators such as moving averages, RSI, and MACD. The model’s task is to predict future stock price movements, which are then used to generate buy, sell, or hold signals.

The process includes:
- Data preprocessing: Stock data is normalized and transformed for input into the LSTM model.
- Model architecture: The LSTM network is designed with multiple layers, including dropout layers to prevent overfitting.
- Model training: The model is trained on historical data, and predictions are made for future price movements.

## Performance Metrics

Once the portfolio is constructed and backtested, the following key performance metrics are calculated to evaluate the strategy:

1. **Portfolio Total Return**: The overall percentage return of the portfolio over the backtest period.
2. **Benchmark Total Return**: The return of the benchmark index (S&P 500) over the same period for comparison.
3. **Compound Annual Growth Rate (CAGR)**: The annualized return, assuming the portfolio grows at a steady rate over the years.
4. **Sharpe Ratio**: A risk-adjusted return measure that compares the portfolio’s excess return (over the risk-free rate) to its volatility.
5. **Maximum Drawdown**: The largest loss from a peak to a trough in the portfolio value, helping assess the risk of the strategy.
6. **Win Rate**: The percentage of days the portfolio's return was positive.
7. **Alpha**: The excess return of the portfolio over the expected return based on the benchmark's performance and the portfolio’s risk (beta).
8. **Beta**: The sensitivity of the portfolio’s returns to the returns of the benchmark. A beta of 1 means the portfolio moves in sync with the benchmark.

  
