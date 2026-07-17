# K-Nearest Neighbors Regressor - Fish Weight Prediction

## Project Overview

This project demonstrates the implementation of the **K-Nearest Neighbors (KNN) Regression** algorithm to predict the **weight of a fish** based on its physical measurements.

Unlike traditional regression algorithms that learn an equation, KNN Regression predicts the target value by averaging the values of the nearest data points in the feature space.

The project includes data preprocessing, missing value handling, feature scaling, automatic selection of the optimal **k**, model evaluation, and visualization of the results.

---

## Dataset

**Dataset:** Fish Market Dataset

### Features

- Species
- Length1
- Length2
- Length3
- Height
- Width

### Target Variable

- Weight

---

## Project Workflow

1. Import Required Libraries
2. Load Dataset
3. Explore Dataset
4. Handle Missing Values
5. Exploratory Data Analysis (EDA)
6. Data Preprocessing
   - Label Encoding
   - Feature Scaling
7. Train-Test Split
8. Find the Best K Value
9. Train KNN Regressor
10. Make Predictions
11. Evaluate Model Performance
12. Visualize Results
13. Key Findings
14. Conclusion

---

## Model Performance

| Metric | Value |
|---------|-------|
| Best K | **1** |
| Mean Absolute Error (MAE) | **60.80** |
| Mean Squared Error (MSE) | **13354.54** |
| Root Mean Squared Error (RMSE) | **115.56** |
| R² Score | **0.9061** |

---

## Key Findings

- Missing values were handled using median imputation.
- Categorical data was converted using Label Encoding.
- Features were standardized using StandardScaler.
- The optimal number of neighbors was automatically selected by comparing K values from **1 to 15**.
- The model achieved an **R² score of 0.9061**, indicating excellent predictive performance.

---

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn

---

## Project Structure

```
K-Nearest Neighbors Regressor - Fish Weight Prediction/
│
├── fish.csv
├── KNN_Regressor_Fish_Weight_Prediction.ipynb
├── README.md
└── requirements.txt
```

---

## Conclusion

The K-Nearest Neighbors Regressor successfully predicted fish weight using physical measurements. After preprocessing the data and selecting the optimal value of **k**, the model achieved excellent performance with an **R² score of 0.9061**, making it an effective regression solution for this dataset.