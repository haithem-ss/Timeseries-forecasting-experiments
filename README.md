# Time Series Forecasting Experiments

An experimental project exploring and comparing different time series forecasting techniques on real-world air passenger traffic data. This project serves as a hands-on laboratory for understanding the strengths and limitations of classical statistical methods versus modern machine learning approaches.

## Overview

This project is a practical exploration of time series analysis, where I experiment with three distinct forecasting methodologies:
- **Classical Decomposition** (Trend + Seasonality)
- **ARIMA** time series modeling
- **Machine Learning** algorithms (Linear Regression, Random Forest, SVR, XGBoost)

The goal is not just to predict, but to understand how different techniques handle temporal patterns, trends, and seasonality in real data.

## Dataset

- **Source**: `US Air Passengers Monthly.csv` (original source unknown, but available via [Google Drive](https://drive.google.com/drive/folders/1SqefV1tuBNinCxd1Hd7GUkm5d3YeN7Ro?usp=drive_link))
- **Training Period**: 2016-2018 (monthly aggregated data)
- **Test Period**: 2019 (first 6 months)
- **Target Variable**: Total passenger count (Sum_PASSENGERS)

> **Note**: I couldn't locate the original data source, but the dataset is available for download via the Google Drive link above.

## Experimental Methodology

### 1. Data Preprocessing
- Conversion of date columns to datetime index
- Monthly resampling and aggregation
- Train/test split (2016-2018 vs 2019)

### 2. Stationarity Analysis
- **Augmented Dickey-Fuller (ADF) Test**: Tests for stationarity
- **Seasonal Decomposition**: Separates the series into:
  - Trend component (linear)
  - Seasonal component
  - Residual component

### 3. Forecasting Approaches

#### Experiment 1: Trend + Seasonality
- Linear regression to model and extrapolate trend
- Addition of historical seasonal patterns
- Simple, interpretable approach

#### Experiment 2: ARIMA Model
- Auto ARIMA for parameter selection
- ARIMA(2,0,2) fitted on detrended series
- Trend component added back to final predictions

#### Experiment 3: Machine Learning
Models tested:
- **Linear Regression**
- **Random Forest Regressor**
- **Support Vector Regressor (SVR)**
- **XGBoost Regressor**

## Project Structure

```
traffic_prediction/
├── main.ipynb      # Main analysis notebook
├── .gitignore      # Git ignore file
└── README.md       # This file
```

> **Note**: The dataset (`US Air Passengers Monthly.csv`) is not included in this repository. Please download it from the [Google Drive link](https://drive.google.com/drive/folders/1SqefV1tuBNinCxd1Hd7GUkm5d3YeN7Ro?usp=drive_link) and place it in the project root directory.

## Results

The notebook produces:
- **Stationarity test results** (ADF test statistics)
- **Decomposition plots** showing trend, seasonality, and residuals
- **ACF/PACF plots** for autocorrelation analysis
- **RMSE comparison** across all prediction methods
- **Visual comparison** of predictions vs actual values for 2019

### Evaluation Metrics
All models are evaluated using **Root Mean Squared Error (RMSE)** on the 2019 test set.

## Key Findings

The results interpretation section in the notebook provides:
- Quantitative RMSE comparison between methods
- Analysis of strengths and weaknesses of each approach
- Insights on model performance and suitability

## Future Experiments

Potential directions to explore:
- Include external variables (economic indicators, fuel prices)
- Test additional ML models (LSTM, Prophet)
- Implement cross-validation for time series
- Extend forecasting horizon
- Add confidence intervals to predictions

---

## Learn More

For a detailed walkthrough of this project, including insights and lessons learned, check out my blog post:

**[Time Series Forecasting Experiments: Classical vs ML Approaches](#)** *(Coming soon)*
