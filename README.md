# VIX Forecasting Project

## Overview
This project focuses on forecasting **U.S. stock-market volatility (VIX)** using multiple time-series approaches: **Prophet**, **ARIMA**, and **LSTM**.  
It also implements **rolling backtesting** to evaluate model stability and performance consistency over time.

---

## Objectives
- Collect and preprocess historical VIX data from Yahoo Finance.  
- Build and compare forecasting models using Prophet, ARIMA, and LSTM.  
- Evaluate model performance using **MAE** and **RMSE**.  
- Apply rolling-window backtesting to assess forecast reliability.  
- Visualize and interpret volatility patterns and prediction accuracy.

---

## Data
- **Source:** Yahoo Finance (`^VIX`)  
- **Market:** U.S. stock market  
- **Period:** 2010 – present  
- **Frequency:** Daily  
- **Target:** VIX closing price – represents expected 30-day volatility of the S&P 500 index.  

---

## Models Implemented

### Prophet
- Captures long-term trend and seasonality in volatility data.  
- Easy to interpret and good for identifying trend reversals.

**Performance:**  
- MAE ≈ *1.92*  
- RMSE ≈ *2.48*

---

### ARIMA
- Classical statistical model used as a baseline for comparison.  
- Performs well in stable market regimes but slower to adapt to sudden spikes.

**Performance:**  
- MAE ≈ *2.11*  
- RMSE ≈ *2.73*

---

### LSTM (Deep Learning)
- Neural network model built with **TensorFlow/Keras**.  
- Learns non-linear and sequential dependencies in the VIX time series.  
- Trained on 60-day look-back windows for 50 epochs.

**Performance:**  
- MAE ≈ *1.54*  
- RMSE ≈ *2.03*  
- Provided smoother, more adaptive short-term forecasts.

---

### Rolling Backtesting
- Dataset extended to start from **2010** to allow multiple training windows.  
- Each iteration trains on a 3-year window and forecasts the next 90 days.  
- Performance metrics aggregated across all windows to measure consistency.

**Backtesting Summary:**  
- Average MAE ≈ *1.60*  
- Average RMSE ≈ *2.10*  
- Stable results confirm strong model generalization.

---

## Results and Insights
- **Prophet** clearly captured long-term trend and seasonality.  
- **ARIMA** provided a stable statistical benchmark.  
- **LSTM** achieved the best short-term accuracy and adapted to volatility shifts.  
- **Backtesting** verified that performance remains consistent over time.  

The LSTM model proved to be the most effective approach for forecasting U.S. market volatility.

---

## Tools and Libraries
`Python`, `pandas`, `numpy`, `yfinance`, `Prophet`, `statsmodels`,  
`TensorFlow / Keras`, `scikit-learn`, `matplotlib`, `seaborn`

---


