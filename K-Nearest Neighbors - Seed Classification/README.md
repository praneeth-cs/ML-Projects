# K-Nearest Neighbors - Seed Classification

A machine learning project that implements the K-Nearest Neighbors (KNN) algorithm to classify wheat seed varieties based on their geometric properties using the Seeds dataset.

## Overview

This project demonstrates a complete multiclass classification workflow using the K-Nearest Neighbors algorithm. It includes data exploration, preprocessing, feature scaling, hyperparameter tuning, model training, prediction, evaluation, and visualization.

The objective is to classify wheat seeds into one of three varieties based on seven physical characteristics.

## Features

- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Feature Scaling using StandardScaler
- Train-Test Split
- Hyperparameter Tuning (Optimal K Selection)
- K-Nearest Neighbors Classification
- Multiclass Classification
- Model Evaluation
- Confusion Matrix
- Classification Report

## Dataset

**Seeds Dataset**

Target Variable:

- Type

The dataset contains seven numerical features describing the geometric properties of wheat kernels:

- Area
- Perimeter
- Compactness
- Kernel Length
- Kernel Width
- Asymmetry Coefficient
- Kernel Groove Length

Target Classes:

- Kama
- Rosa
- Canadian

### Dataset Source

Seeds Dataset. UCI Machine Learning Repository.

Available from:

https://archive.ics.uci.edu/ml/datasets/seeds

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Repository Contents

```text
├── seed_classification_knn.ipynb
├── Seed_Data.csv
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

## Results

The K-Nearest Neighbors classifier successfully classifies wheat seed varieties based on their physical measurements. Hyperparameter tuning is performed to determine the optimal value of K, improving the overall predictive performance of the model.