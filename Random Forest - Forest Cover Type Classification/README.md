# Random Forest - Forest Cover Type Classification

A machine learning project that implements a Random Forest classifier to predict forest cover types using cartographic variables from the Forest Cover Type dataset.

## Overview

This project demonstrates a complete multiclass classification workflow using the Random Forest algorithm. It includes data exploration, preprocessing, model training, prediction, evaluation, and feature importance analysis.

The objective is to classify forest cover into one of seven cover types based on geographical and environmental characteristics.

## Features

- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Train-Test Split
- Random Forest Classification
- Multiclass Classification
- Model Evaluation
- Confusion Matrix
- Classification Report
- Feature Importance Visualization

## Dataset

**Forest Cover Type Dataset**

Target Variable:

- Cover_Type

The dataset contains cartographic variables describing forested areas, including:

- Elevation
- Aspect
- Slope
- Horizontal Distance to Hydrology
- Vertical Distance to Hydrology
- Horizontal Distance to Roadways
- Hillshade (9am, Noon, 3pm)
- Horizontal Distance to Fire Points
- Wilderness Area Indicators
- Soil Type Indicators

Target Classes:

- Spruce/Fir
- Lodgepole Pine
- Ponderosa Pine
- Cottonwood/Willow
- Aspen
- Douglas-fir
- Krummholz

### Dataset Source

Blackard, J.A. & Dean, D.J. (1999).

Forest Cover Type [dataset].

UCI Machine Learning Repository.

Available from: https://archive.ics.uci.edu/dataset/31/covertype

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Repository Contents

```text
├── random_forest_forest_cover_type_classification.ipynb
├── covtype.csv
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

- Class Distribution
- Correlation Analysis
- Confusion Matrix
- Feature Importance

## Results

The Random Forest classifier successfully predicts forest cover types using environmental and cartographic variables. Feature importance analysis highlights the variables that contribute most to model performance, demonstrating the effectiveness of ensemble learning for multiclass classification problems.