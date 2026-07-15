# Random Forest Regressor - Medical Insurance Cost Prediction

A machine learning project that implements the Random Forest Regressor algorithm to predict individual medical insurance costs based on demographic and health-related attributes.

## Overview

This project demonstrates a complete regression workflow using the Random Forest Regressor algorithm. The notebook includes data exploration, preprocessing, model training, prediction, evaluation, and feature importance analysis.

The objective is to predict medical insurance charges using personal attributes such as age, BMI, smoking status, number of children, sex, and region.

## Features

- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Data Preprocessing
- Label Encoding
- Train-Test Split
- Random Forest Regression
- Model Evaluation
- Feature Importance
- Actual vs Predicted Visualization
- Residual Analysis

## Dataset

**Medical Insurance Cost Prediction Dataset**

Target Variable:

- `charges`

Input Features:

- age
- sex
- bmi
- children
- smoker
- region

### Dataset Source

Medical Cost Personal Dataset

Available from:

https://www.kaggle.com/datasets/mirichoi0218/insurance

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Repository Contents

```text
├── medical_insurance_cost_random_forest_regressor.ipynb
├── insurance.csv
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

- Distribution of Insurance Charges
- Correlation Heatmap
- Actual vs Predicted Values
- Residual Plot
- Feature Importance

## Results

The Random Forest Regressor achieved strong predictive performance with an **R² Score of approximately 0.86**, explaining around **86% of the variation** in medical insurance charges. Compared to a single Decision Tree Regressor, the ensemble model significantly reduced prediction error, demonstrating the effectiveness of bagging for regression tasks and its ability to improve generalization while reducing overfitting.