# Support Vector Machine - Dry Bean Classification

A machine learning project that implements a Support Vector Machine (SVM) classifier to identify dry bean varieties based on their morphological characteristics using the Dry Bean dataset.

## Overview

This project demonstrates a complete multiclass classification workflow using the Support Vector Machine (SVM) algorithm. It includes data exploration, preprocessing, feature scaling, model training, prediction, evaluation, and visualization.

The objective is to classify dry beans into one of seven bean varieties using numerical shape and size features.

## Features

- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Correlation Heatmap
- Feature Scaling using StandardScaler
- Train-Test Split
- Support Vector Machine (RBF Kernel)
- Multiclass Classification
- Model Evaluation
- Confusion Matrix
- Classification Report

## Dataset

**Dry Bean Dataset**

Target Variable:

- Class

Bean Classes:

- BARBUNYA
- BOMBAY
- CALI
- DERMASON
- HOROZ
- SEKER
- SIRA

### Dataset Source

Dry Bean [dataset]. 2020. UCI Machine Learning Repository.

Available from: https://doi.org/10.24432/C50S4B

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- OpenPyXL

## Repository Contents

```text
├── dry_bean_classification_svm.ipynb
├── Dry_Bean_Dataset.csv
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

The Support Vector Machine classifier successfully performs multiclass classification across seven dry bean varieties. Feature scaling improves model performance, while the confusion matrix and classification report provide detailed insights into prediction accuracy for each bean class.