# Support Vector Regressor - Concrete Strength Prediction

A machine learning project that implements the Support Vector Regressor (SVR) algorithm to predict the compressive strength of concrete using material composition and curing age.

## Overview

This project demonstrates a complete regression workflow using the Support Vector Regressor (SVR) algorithm. The notebook covers data loading, preprocessing, feature scaling, model training, prediction, evaluation, and visualization.

The objective is to predict the compressive strength of concrete based on its ingredients and curing age. Since SVR relies on distance-based optimization, feature scaling is an essential preprocessing step and is included in this project.

## Features

- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Data Preprocessing
- Feature Scaling using StandardScaler
- Train-Test Split
- Support Vector Regression (SVR)
- Model Evaluation
- Actual vs Predicted Visualization
- Residual Analysis

## Dataset

**Concrete Compressive Strength Dataset**

Target Variable:

- Concrete Compressive Strength

Input Features:

- Cement
- Blast Furnace Slag
- Fly Ash
- Water
- Superplasticizer
- Coarse Aggregate
- Fine Aggregate
- Age

### Dataset Source

Concrete Compressive Strength Dataset

Available from:

https://www.kaggle.com/datasets/elikplim/concrete-compressive-strength-data-set

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Repository Contents

```text
├── support_vector_regressor_concrete_strength_prediction.ipynb
├── concrete_data.csv
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

- Correlation Heatmap
- Actual vs Predicted Values
- Residual Plot

## Results

The Support Vector Regressor achieved excellent predictive performance with an **R² Score of approximately 0.87**, explaining around **87% of the variation** in concrete compressive strength. After feature scaling, the SVR model effectively captured the nonlinear relationships within the data, demonstrating why kernel-based methods are well suited for numerical regression problems.