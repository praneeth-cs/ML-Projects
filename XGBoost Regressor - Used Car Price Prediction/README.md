# XGBoost Regressor - Used Car Price Prediction

## Project Overview

This project implements an **XGBoost Regressor** to predict used-car sale prices using a dataset containing vehicle specifications, pricing information, location details, and other attributes.

The project demonstrates a complete machine learning regression workflow, including data exploration, missing-value handling, categorical feature encoding, model training, evaluation, feature importance analysis, and investigation of potential target leakage.

An initial XGBoost model achieved an exceptionally high **R² score of 0.9869**. Feature importance analysis revealed that several financing-related variables were highly influential. Since these variables could contain information directly or indirectly derived from the sale price, a second leakage-controlled model was trained after removing potentially price-derived features.

The leakage-controlled model achieved an **R² score of 0.9291**, demonstrating strong predictive performance while providing a more realistic assessment of the model's ability to predict used-car prices.

---

## Dataset

The dataset contains approximately **7,400 used-car records** and **29 original columns**.

The target variable is:

- `sale_price`

The dataset contains a combination of:

- Numerical vehicle attributes
- Categorical vehicle information
- Location information
- Vehicle condition and rating information
- Pricing and financing-related attributes

---

## Project Workflow

1. Project Overview
2. Import Required Libraries
3. Load Dataset
4. Explore Dataset
5. Missing Values and Duplicates
6. Data Cleaning
7. Exploratory Data Analysis
8. Prepare Features and Target
9. Preprocessing Pipeline
10. Train-Test Split
11. Train XGBoost Regressor
12. Make Predictions
13. Model Evaluation
14. Actual vs Predicted Prices
15. Residual Analysis
16. Feature Importance
17. Potential Target Leakage Analysis
18. Key Findings
19. Conclusion

---

## Data Preprocessing

The dataset contains missing values in several columns, including:

- `original_price`
- `car_availability`
- `transmission`
- `source`
- `body_type`
- `registered_state`
- `registered_city`
- `car_rating`
- `fitness_certificate`
- `ad_created_on`

Instead of removing a large number of observations, missing values are handled through the preprocessing pipeline.

### Numerical Features

Missing numerical values are handled using **median imputation**.

### Categorical Features

Missing categorical values are handled using **most-frequent-value imputation**.

Categorical variables are transformed using **One-Hot Encoding**, with unknown categories handled automatically during prediction.

---

## Model

The primary machine learning algorithm used in this project is:

**XGBoost Regressor**

The model uses gradient-boosted decision trees, where trees are built sequentially and each new tree attempts to correct errors made by the previous trees.

The model configuration includes parameters such as:

- `n_estimators`
- `learning_rate`
- `max_depth`
- `subsample`
- `colsample_bytree`

---

## Model Evaluation

The regression models are evaluated using:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

### Full-Feature Model Results

| Metric | Result |
|---|---:|
| MAE | 3,563.71 |
| RMSE | 34,327.36 |
| R² Score | 0.9869 |

The initial model explained approximately **98.69% of the variance** in used-car sale prices.

---

## Feature Importance and Target Leakage Analysis

Feature importance analysis showed that the most influential features included:

- `emi_starts_from`
- `booking_down_pymnt`
- `source`
- `is_hot`
- `car_rating`
- `city`
- `variant`
- `broker_quote`
- `car_name`
- `fuel_type`

The unusually high importance of `emi_starts_from` and `booking_down_pymnt` raised concerns about potential **target leakage**.

Financing-related variables such as EMI and down payment may be directly calculated from or strongly influenced by a vehicle's sale price. The `broker_quote` variable may similarly contain price-related information.

To obtain a more realistic evaluation, the following potentially price-derived features were removed:

- `emi_starts_from`
- `booking_down_pymnt`
- `broker_quote`

A second XGBoost model was then trained using the leakage-controlled feature set.

---

## Leakage-Controlled Model Results

| Metric | Full-Feature Model | Leakage-Controlled Model |
|---|---:|---:|
| MAE | 3,563.71 | 35,335.88 |
| RMSE | 34,327.36 | 79,944.61 |
| R² Score | 0.9869 | **0.9291** |

Although performance decreased after removing the potentially price-derived features, the leakage-controlled model still explained approximately **92.91% of the variance** in used-car sale prices.

The leakage-controlled result is considered the more realistic primary performance estimate for this project.

---

## Key Findings

- XGBoost demonstrated strong performance for used-car price prediction using structured tabular data.
- Missing values were handled using median imputation for numerical features and most-frequent-value imputation for categorical features.
- One-Hot Encoding was used to transform categorical variables into a format suitable for machine learning.
- The initial full-feature XGBoost model achieved an exceptionally high **R² score of 0.9869**.
- Feature importance analysis identified `emi_starts_from` and `booking_down_pymnt` as the two dominant predictors.
- These financing-related features, along with `broker_quote`, were identified as potential sources of target leakage because they may contain information derived from or strongly related to the target sale price.
- After removing the potentially price-derived features, the leakage-controlled model achieved an **R² score of 0.9291**.
- The leakage-controlled model retained strong predictive performance, explaining approximately **92.9% of the variance** in used-car sale prices.
- Investigating feature importance and potential target leakage resulted in a more credible evaluation of the model's real-world predictive capability.

---

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook

---

## Project Structure

```text
XGBoost Regressor - Used Car Price Prediction/
│
├── Used_Car_Price_Prediction.csv
├── xgboost_regressor_used_car_price_prediction_updated.ipynb
├── README.md
└── requirements.txt
```

---

## Conclusion

This project demonstrated an end-to-end implementation of **XGBoost Regression** for used-car price prediction.

The initial full-feature model achieved an R² score of **0.9869**, indicating exceptionally high predictive performance. However, feature importance analysis revealed that financing-related variables were dominating the model's predictions and could potentially introduce target leakage.

After removing `emi_starts_from`, `booking_down_pymnt`, and `broker_quote`, the leakage-controlled XGBoost model achieved an **R² score of 0.9291**. Although the prediction error increased, the leakage-controlled result provides a more realistic estimate of the model's ability to predict sale prices using independent vehicle characteristics.

Overall, the project demonstrates not only the predictive capabilities of XGBoost but also the importance of examining feature importance, identifying potential target leakage, and critically evaluating unusually high model performance.