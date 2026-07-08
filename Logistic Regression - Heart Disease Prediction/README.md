# Logistic Regression - Heart Disease Prediction

A machine learning project that implements a Logistic Regression model to predict the presence of heart disease using the Cleveland Heart Disease dataset.

## Overview

This project demonstrates a complete binary classification workflow, including data exploration, preprocessing, feature scaling, model training, prediction, evaluation, and visualization.

The objective is to classify whether a patient is likely to have heart disease based on various clinical attributes.

## Features

- Exploratory Data Analysis (EDA)
- Correlation Heatmap
- Feature Scaling
- Train-Test Split
- Logistic Regression Model
- Model Evaluation
- Confusion Matrix
- Classification Report
- ROC Curve
- ROC-AUC Score

## Dataset

**Cleveland Heart Disease Dataset**

Target Variable:
- `target`

Features include:

- Age
- Sex
- Chest Pain Type
- Resting Blood Pressure
- Cholesterol
- Fasting Blood Sugar
- Resting ECG
- Maximum Heart Rate
- Exercise-Induced Angina
- ST Depression
- Slope
- Number of Major Vessels
- Thalassemia

### Dataset Source

- UCI Machine Learning Repository
- Kaggle (Cleveland Heart Disease Dataset)

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Repository Contents

```text
├── heart_disease_prediction_logistic_regression.ipynb
├── Heart_disease_cleveland.csv
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
- ROC Curve
- ROC-AUC Score

## Results

The Logistic Regression classifier predicts the presence of heart disease and is evaluated using standard binary classification metrics. The ROC Curve and Confusion Matrix provide additional insight into the model's classification performance.