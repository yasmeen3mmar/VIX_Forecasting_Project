# VIX Forecasting Project

## Overview
This project focuses on forecasting **U.S. stock-market volatility (VIX)** using three different time-series approaches: **Prophet**, **ARIMA**, and **LSTM**.  
It also implements a **rolling backtesting** framework to evaluate how stable and reliable each model’s forecasts remain over time.

---

## Objectives
- Collect and preprocess historical VIX data from Yahoo Finance.  
- Build and compare forecasting models using Prophet, ARIMA, and LSTM.  
- Evaluate model performance using **MAE** and **RMSE**.  
- Apply rolling-window backtesting to assess forecast consistency.  
- Visualize and interpret volatility patterns and model accuracy.

---

## Data
- **Source:** Yahoo Finance (`^VIX`)  
- **Market:** U.S. stock market  
- **Main run period:** 2018-01-01 to July 2025 (the last notebook execution)  
- **Extended period for backtesting:** 2010-01-01 to July 2025  
- **Frequency:** Daily closing prices  
- **Target:** VIX closing price — represents expected 30-day volatility of the S&P 500 Index.

---

## Models Implemented

### Prophet
Captures long-term trend and seasonality in volatility data.  
Easy to interpret and useful for identifying broad market behavior.

**Performance:**  
- MAE ≈ 1.92  
- RMSE ≈ 2.48  

---

### ARIMA
A classical statistical model used as a benchmark for comparison.  
Performs well in stable periods but reacts slowly to sudden volatility spikes.

**Performance:**  
- MAE ≈ 2.11  
- RMSE ≈ 2.73  

---

### LSTM (Deep Learning)
Neural-network model built with **TensorFlow/Keras** to capture sequential and non-linear patterns.  
Trained on 60-day look-back windows for 50 epochs.

**Performance:**  
- MAE ≈ 1.54  
- RMSE ≈ 2.03  
- Produced smoother and more adaptive short-term forecasts.

---

### Rolling Backtesting
To evaluate stability, the dataset was reloaded starting from **2010-01-01 to July 2025** to allow multiple rolling windows.

Process:
1. Train on an initial 3-year window.  
2. Forecast the next 90 days.  
3. Slide the window forward and repeat.  
4. Aggregate MAE / RMSE across all iterations.

**Backtesting Summary:**  
- Average MAE ≈ 1.60  
- Average RMSE ≈ 2.10  
- Stable results confirm strong model generalization.

---

## Results and Insights
- **Prophet** clearly modeled long-term trend and seasonal patterns.  
- **ARIMA** provided a consistent statistical baseline.  
- **LSTM** achieved the best short-term accuracy and adapted better to volatility shifts.  
- **Backtesting** verified that the models maintain consistent performance over time.  

Overall, the **LSTM** model proved to be the most effective approach for forecasting U.S. market volatility.

---

## Tools and Libraries
`Python`, `pandas`, `numpy`, `yfinance`, `Prophet`, `statsmodels`, `TensorFlow / Keras`, `scikit-learn`, `matplotlib`, `seaborn`

---


