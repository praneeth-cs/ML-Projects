# Decision Tree Regressor - California Housing Price Prediction

A machine learning project that implements the Decision Tree Regressor algorithm to predict median house values using the California Housing dataset.

## Overview

This project demonstrates a complete regression workflow using the Decision Tree Regressor algorithm. The notebook covers data exploration, preprocessing, model training, prediction, evaluation, and feature importance analysis.

The objective is to predict the median house value of California districts based on demographic, geographic, and housing-related attributes.

## Features

- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Data Preprocessing
- Label Encoding
- Train-Test Split
- Decision Tree Regression
- Model Evaluation
- Feature Importance
- Actual vs Predicted Visualization
- Residual Analysis

## Dataset

**California Housing Dataset**

Target Variable:

- `median_house_value`

Input Features:

- longitude
- latitude
- housing_median_age
- total_rooms
- total_bedrooms
- population
- households
- median_income
- ocean_proximity

### Dataset Source

California Housing Prices Dataset

Available from:

https://www.kaggle.com/datasets/camnugent/california-housing-prices

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Repository Contents

```text
├── house_price_prediction_decision_tree_regressor.ipynb
├── housing.csv
├── README.md
└── requirements.txt
```

## Evaluation Metrics

The regression model is evaluated using:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

## Visualizations

- Distribution of Target Variable
- Correlation Heatmap
- Actual vs Predicted Values
- Residual Plot
- Feature Importance

## Results

The Decision Tree Regressor successfully predicts California housing prices based on geographical and demographic features. The model achieved a good baseline performance with an R² Score of approximately **0.71**, demonstrating that it can explain around 71% of the variation in house prices. This project illustrates how decision trees can be applied to regression problems and highlights the importance of controlling model complexity to reduce overfitting.