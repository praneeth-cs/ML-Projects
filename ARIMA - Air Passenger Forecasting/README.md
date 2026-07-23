# ARIMA - Air Passenger Forecasting

## Project Overview

This project analyzes and forecasts monthly airline passenger counts using classical **time-series modeling**.

The notebook builds toward ARIMA by examining stationarity, differencing, **ACF/PACF**, and separate **AutoRegressive (AR)** and **Moving Average (MA)** models before training and evaluating an **ARIMA** model.

---

## Dataset

The dataset contains **144 monthly observations** from **January 1949 to December 1960**.

| Column | Description |
|---|---|
| `Month` | Monthly timestamp |
| `Passengers` | Number of airline passengers |

The dataset was obtained from the **AirPassengers time-series dataset**:

https://www.kaggle.com/datasets/chirag19/air-passengers

The dataset contains no missing values.

---

## Project Workflow

1. Import Required Libraries
2. Load Dataset
3. Prepare Time Series
4. Explore Dataset
5. Time-Series Visualization
6. Stationarity Analysis
7. Differencing
8. ACF and PACF Analysis
9. Chronological Train-Test Split
10. AutoRegressive (AR) Model
11. Moving Average (MA) Model
12. ARIMA Model
13. Train and Evaluate ARIMA
14. Model Performance Comparison
15. Actual vs Predicted Values
16. Residual Diagnostics
17. Future Forecasting
18. Key Findings
19. Conclusion

---

## Stationarity Analysis

The original passenger series was strongly non-stationary according to the Augmented Dickey-Fuller test:

- **ADF statistic:** 0.8154
- **p-value:** 0.991880

After first differencing:

- **ADF statistic:** -2.8293
- **p-value:** 0.054213

Differencing substantially improved stationarity, although the p-value remained slightly above the conventional 0.05 threshold.

---

## Train-Test Split

The time series was split chronologically rather than randomly:

- **Training observations:** 120
- **Testing observations:** 24
- **Training period:** January 1949 – December 1958
- **Testing period:** January 1959 – December 1960

---

## Model Performance

| Model | MAE | RMSE |
|---|---:|---:|
| **AR(12)** | **21.452** | **27.073** |
| ARIMA(2,1,2) | 69.105 | 90.703 |
| MA(2) | 71.886 | 96.545 |

Among the evaluated models, **AR(12)** achieved the lowest MAE and RMSE by a substantial margin.

The ARIMA candidate models were compared using AIC, with **ARIMA(2,1,2)** selected as the best non-seasonal ARIMA specification from the tested candidates.

---

## Key Findings

- The AirPassengers series contains a clear upward trend and strong recurring temporal structure.
- The original series was non-stationary, with an ADF p-value of **0.991880**.
- First differencing reduced the ADF p-value to **0.054213**, bringing the series close to the conventional 5% stationarity threshold.
- ACF and PACF analysis showed substantial lag dependence in the time series.
- **AR(12)** achieved the best forecasting performance with an MAE of **21.452** and RMSE of **27.073**.
- The **MA(2)** model performed considerably worse, with an MAE of **71.886** and RMSE of **96.545**.
- Among the tested ARIMA specifications, **ARIMA(2,1,2)** had the lowest AIC and was selected for evaluation.
- ARIMA(2,1,2) achieved an MAE of **69.105** and RMSE of **90.703**, substantially worse than AR(12).
- The strong performance of AR(12) indicates that longer lag relationships are important in this monthly passenger series.
- The results also show a limitation of non-seasonal ARIMA for data with strong seasonal behavior, motivating the use of **SARIMA** as a future extension.

---

## Future Forecast

The selected ARIMA(2,1,2) model was refitted on the complete dataset and used to generate a **12-month forecast for 1961**.

The forecast ranges from approximately **439.85 passengers in January 1961**, rises to approximately **571.31 in June**, and then declines toward approximately **449.70 in December**.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Statsmodels
- Jupyter Notebook

---

## Project Structure

```text
ARIMA - Air Passenger Forecasting/
│
├── AirPassengers.csv
├── arima_air_passenger_forecasting.ipynb
├── README.md
└── requirements.txt
```

---

## Conclusion

This project demonstrated the progression from basic autoregressive and moving-average models to **ARIMA forecasting** on the AirPassengers time series.

The original series was strongly non-stationary, and first differencing substantially improved its stationarity. ACF and PACF analysis provided insight into the lag relationships present in the data.

Of the evaluated models, **AR(12) performed best**, achieving an MAE of **21.452** and RMSE of **27.073**. The selected non-seasonal **ARIMA(2,1,2)** model produced considerably larger errors, with an MAE of **69.105** and RMSE of **90.703**.

The results indicate that the strong recurring yearly structure in the monthly passenger data is important for forecasting. While ARIMA provides a useful foundation for time-series modeling, explicitly modeling seasonality with **SARIMA** is a logical next step for this dataset.
