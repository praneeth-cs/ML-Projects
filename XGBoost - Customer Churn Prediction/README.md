# XGBoost - Customer Churn Prediction

A machine learning project that implements the XGBoost (Extreme Gradient Boosting) algorithm to predict customer churn using the IBM Telco Customer Churn dataset.

## Overview

This project demonstrates a complete binary classification workflow using the XGBoost algorithm. It includes data loading, preprocessing, exploratory data analysis, feature encoding, model training, prediction, evaluation, and feature importance analysis.

The objective is to predict whether a customer is likely to discontinue a telecommunications service based on demographic information, account details, and subscribed services.

## Features

- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Data Cleaning
- Feature Encoding
- Train-Test Split
- XGBoost Classification
- Binary Classification
- Model Evaluation
- Confusion Matrix
- Classification Report
- Feature Importance

## Dataset

**IBM Telco Customer Churn Dataset**

Target Variable:

- Churn

Classes:

- Yes
- No

The dataset contains customer information including:

- Customer Demographics
- Account Information
- Contract Type
- Internet Service
- Payment Method
- Monthly Charges
- Total Charges
- Tenure
- Additional Services

### Dataset Source

IBM Sample Data.

Available through Kaggle:

https://www.kaggle.com/datasets/blastchar/telco-customer-churn

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost

## Repository Contents

```text
├── customer_churn_xgboost.ipynb
├── customer_churn.csv
├── README.md
└── requirements.txt
```

## Evaluation Metrics

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Classification Report

## Visualizations

- Churn Distribution
- Correlation Heatmap
- Confusion Matrix
- Feature Importance

## Results

The XGBoost classifier successfully predicts customer churn using customer demographic and service-related information. The project demonstrates how gradient boosting can effectively model complex relationships in structured business data while providing insights into the features that contribute most to customer retention.