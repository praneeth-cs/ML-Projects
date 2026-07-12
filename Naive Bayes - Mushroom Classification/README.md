# Naive Bayes - Mushroom Classification

A machine learning project that implements the Naive Bayes algorithm to classify mushrooms as edible or poisonous based on their physical characteristics.

## Overview

This project demonstrates a complete binary classification workflow using the Gaussian Naive Bayes algorithm. The workflow includes data exploration, preprocessing, categorical feature encoding, model training, prediction, and evaluation.

The objective is to classify mushrooms into edible or poisonous categories using descriptive physical attributes.

## Features

- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Label Encoding of Categorical Features
- Train-Test Split
- Gaussian Naive Bayes Classification
- Binary Classification
- Model Evaluation
- Confusion Matrix
- Classification Report

## Dataset

**Mushroom Dataset**

Target Variable:

- class

Classes:

- e — Edible
- p — Poisonous

The dataset contains categorical features describing mushroom characteristics, including:

- Cap Shape
- Cap Surface
- Cap Color
- Bruises
- Odor
- Gill Attachment
- Gill Spacing
- Gill Size
- Gill Color
- Stalk Shape
- Stalk Root
- Ring Type
- Spore Print Color
- Population
- Habitat

### Dataset Source

Schlimmer, J. (1987).

*Mushroom* [dataset].

UCI Machine Learning Repository.

Available from:

https://archive.ics.uci.edu/dataset/73/mushroom

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Repository Contents

```text
├── mushroom_classification_naive_bayes.ipynb
├── mushrooms.csv
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
- Correlation Heatmap
- Confusion Matrix

## Results

The Naive Bayes classifier successfully classified mushrooms as edible or poisonous based on their physical characteristics. The project demonstrates how probabilistic machine learning models can perform effective classification after appropriate preprocessing and feature encoding.