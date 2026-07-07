# Linear Regression - Energy Efficiency Prediction

A machine learning project that implements a Linear Regression model to predict the heating load of residential buildings based on their architectural characteristics using the Energy Efficiency dataset.

## Overview

This project demonstrates a complete regression workflow, including data exploration, preprocessing, feature analysis, model training, prediction, evaluation, and visualization.

The objective is to predict a building's **Heating Load** using eight architectural features such as relative compactness, surface area, roof area, glazing area, and overall height.

## Features

- Exploratory Data Analysis (EDA)
- Correlation Heatmap
- Feature Selection
- Train-Test Split
- Linear Regression Model
- Model Evaluation
- Actual vs Predicted Visualization
- Residual Analysis

## Dataset

**Energy Efficiency Dataset**

Target Variable:
- Heating Load

Features:
- Relative Compactness
- Surface Area
- Wall Area
- Roof Area
- Overall Height
- Orientation
- Glazing Area
- Glazing Area Distribution

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Repository Contents

```text
├── energy_efficiency_prediction_linear_regression.ipynb
├── energy_efficiency_data.csv
├── README.md
└── requirements.txt
```

## Evaluation Metrics

The model is evaluated using:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

Visual evaluation includes:

- Actual vs Predicted Plot
- Residual Plot

## Results

The trained Linear Regression model demonstrates strong predictive performance for estimating building heating load. The evaluation metrics and visualizations indicate that the model captures the relationship between architectural features and energy efficiency effectively.