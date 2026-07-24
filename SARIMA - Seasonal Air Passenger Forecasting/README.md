# SARIMA - Seasonal Air Passenger Forecasting

## Project Overview

This project extends non-seasonal ARIMA forecasting by explicitly modeling the **12-month seasonal pattern** in the AirPassengers dataset using **SARIMA (Seasonal AutoRegressive Integrated Moving Average)**.

The notebook covers seasonal decomposition, stationarity analysis, seasonal differencing, ACF/PACF analysis, an ARIMA baseline, SARIMA model selection, forecast evaluation, confidence intervals, residual diagnostics, and future forecasting.

---

## Dataset

The AirPassengers dataset contains **144 monthly observations** from **January 1949 to December 1960**.

| Column | Description |
|---|---|
| `Month` | Monthly timestamp |
| `Passengers` | Number of airline passengers |

The dataset contains no missing values.

### Dataset Source

The dataset was obtained from the **AirPassengers time-series dataset**:

https://www.kaggle.com/datasets/chirag19/air-passengers

---

## Project Workflow

1. Import Required Libraries
2. Load Dataset
3. Prepare Time Series
4. Explore Dataset
5. Time-Series Visualization
6. Seasonal Decomposition
7. Stationarity Analysis
8. Seasonal Differencing
9. ACF and PACF Analysis
10. Chronological Train-Test Split
11. ARIMA Baseline
12. SARIMA Model
13. Train and Evaluate SARIMA
14. ARIMA vs SARIMA Comparison
15. Actual vs Predicted Values
16. SARIMA Forecast Confidence Interval
17. Residual Diagnostics
18. Future Forecasting
19. Key Findings
20. Conclusion

---

## Seasonal Analysis

The original AirPassengers series contains an upward trend and strong recurring yearly seasonality.

The original series was strongly non-stationary:

- **ADF statistic:** 0.8154
- **p-value:** 0.991880

After applying **12-month seasonal differencing**:

- **ADF statistic:** -3.3830
- **p-value:** 0.011551

Since the seasonally differenced p-value is below 0.05, the transformed series provides evidence of stationarity at the conventional 5% significance level.

---

## Train-Test Split

The time series was split chronologically:

- **Training observations:** 120
- **Testing observations:** 24
- **Training period:** January 1949 – December 1958
- **Testing period:** January 1959 – December 1960

The final two years were retained for out-of-sample evaluation.

---

## ARIMA Baseline

The non-seasonal **ARIMA(2,1,2)** model from the preceding ARIMA project was used as the baseline.

| Metric | Result |
|---|---:|
| MAE | 69.105 |
| RMSE | 90.703 |

---

## SARIMA Model Selection

Several SARIMA specifications were compared using **AIC**.

The selected model was:

**SARIMA(0,1,1)(0,1,1,12)**

with an AIC of approximately **707.509**.

The seasonal period `12` represents the yearly cycle in monthly passenger data.

---

## ARIMA vs SARIMA

| Model | MAE | RMSE |
|---|---:|---:|
| ARIMA(2,1,2) | 69.105 | 90.703 |
| **SARIMA(0,1,1)(0,1,1,12)** | **66.275** | **71.829** |

SARIMA achieved lower MAE and substantially lower RMSE than the non-seasonal ARIMA baseline.

---

## Future Forecast

The selected SARIMA model was refitted using the complete dataset and used to forecast passenger counts for the next **12 months**.

The forecast preserves the recurring seasonal pattern, increasing through the middle of the year and reaching approximately **649.81 passengers in July 1961** before declining later in the year.

The notebook also reports **95% forecast confidence intervals** to represent uncertainty around the predicted values.

---

## Key Findings

- The AirPassengers series contains a clear upward trend and strong **12-month seasonal structure**.
- The original series was non-stationary, with an ADF p-value of **0.991880**.
- Applying 12-month seasonal differencing reduced the ADF p-value to **0.011551**, providing evidence of stationarity at the 5% significance level.
- ACF and PACF analysis was used to inspect the remaining lag relationships after seasonal differencing.
- The non-seasonal ARIMA(2,1,2) baseline achieved an MAE of **69.105** and RMSE of **90.703**.
- Among the tested SARIMA candidates, **SARIMA(0,1,1)(0,1,1,12)** achieved the lowest AIC at approximately **707.509**.
- The selected SARIMA model achieved an MAE of **66.275** and RMSE of **71.829**.
- SARIMA improved both evaluation metrics compared with ARIMA, with the largest improvement occurring in RMSE.
- The results demonstrate the value of explicitly modeling seasonality when forecasting data with a strong recurring seasonal cycle.
- The final 12-month SARIMA forecast retains the yearly passenger pattern and includes 95% confidence intervals to represent forecast uncertainty.

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
SARIMA - Seasonal Air Passenger Forecasting/
│
├── AirPassengers.csv
├── sarima_seasonal_air_passenger_forecasting.ipynb
├── README.md
└── requirements.txt
```

---

## Conclusion

This project demonstrated how **SARIMA extends ARIMA by explicitly modeling seasonal behavior** in time-series data.

The original AirPassengers series was strongly non-stationary. Applying 12-month seasonal differencing reduced the ADF p-value from **0.991880 to 0.011551**, providing evidence that the seasonally differenced series was stationary at the conventional 5% significance level.

The non-seasonal ARIMA(2,1,2) baseline achieved an MAE of **69.105** and RMSE of **90.703**. After comparing multiple seasonal specifications, **SARIMA(0,1,1)(0,1,1,12)** was selected and achieved an improved MAE of **66.275** and RMSE of **71.829**.

Overall, SARIMA provided better out-of-sample forecasting performance than the non-seasonal ARIMA baseline, particularly in RMSE. The results demonstrate that explicitly incorporating the 12-month seasonal cycle can improve forecasting for strongly seasonal monthly time-series data.
