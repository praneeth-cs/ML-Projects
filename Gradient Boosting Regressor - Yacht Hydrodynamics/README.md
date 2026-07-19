# Gradient Boosting Regressor - Yacht Hydrodynamics

## Project Overview

This project implements a **Gradient Boosting Regressor** to predict the **residuary resistance of sailing yachts** using hydrodynamic and hull-design characteristics.

Gradient Boosting builds decision trees sequentially, with each new tree attempting to reduce prediction errors made by the existing ensemble. The project covers data exploration, data-quality checks, exploratory data analysis, model training, regression evaluation, residual analysis, and feature importance analysis.

## Dataset

The Yacht Hydrodynamics dataset contains **308 observations** with six input features and one target variable:

- `LC` - Longitudinal position of the center of buoyancy
- `PC` - Prismatic coefficient
- `L/D` - Length-displacement ratio
- `B/Dr` - Beam-draught ratio
- `L/B` - Length-beam ratio
- `Fr` - Froude number
- `Rr` - Residuary resistance (target)

## Project Workflow

1. Import Required Libraries
2. Load Dataset
3. Explore Dataset
4. Check Missing Values and Duplicates
5. Data Cleaning
6. Exploratory Data Analysis
7. Prepare Features and Target
8. Train-Test Split
9. Train Gradient Boosting Regressor
10. Make Predictions
11. Model Evaluation
12. Actual vs Predicted Values
13. Residual Analysis
14. Feature Importance
15. Key Findings
16. Conclusion

## Model Performance

| Metric | Result |
|---|---:|
| Mean Absolute Error (MAE) | 0.26 |
| Mean Squared Error (MSE) | 0.32 |
| Root Mean Squared Error (RMSE) | 0.57 |
| R² Score | 0.9978 |

The model achieved an **R² score of 0.9978**, explaining approximately **99.78% of the variance** in residuary resistance on the selected test split.

## Feature Importance

Feature importance analysis showed that the **Froude number (`Fr`)** was overwhelmingly the most influential feature in the trained model. The **prismatic coefficient (`PC`)** provided a smaller secondary contribution.

The relatively low model importance of the remaining features does not imply that they lack physical significance; it indicates that they provided less additional predictive information for this particular trained model and dataset.

## Key Findings

- The Gradient Boosting Regressor achieved excellent predictive performance.
- The model achieved an **MAE of 0.26** and an **RMSE of 0.57**.
- The **R² score of 0.9978** indicates that approximately **99.78% of the variance** in residuary resistance was explained on the test split.
- The **Froude number (`Fr`)** was the dominant predictive feature.
- The **prismatic coefficient (`PC`)** provided a smaller secondary contribution.
- Gradient Boosting effectively captured nonlinear relationships in the structured numerical dataset.
- Since the dataset contains only 308 observations, cross-validation could be used in future work for a more robust estimate of generalization performance.

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Structure

```text
Gradient Boosting Regressor - Yacht Hydrodynamics/
│
├── yacht_hydrodynamics.csv
├── gradient_boosting_regressor_yacht_hydrodynamics.ipynb
├── README.md
└── requirements.txt
```

## Conclusion

This project demonstrated the implementation of a **Gradient Boosting Regressor** for predicting yacht residuary resistance using hydrodynamic and hull-design characteristics.

The model achieved excellent performance, with an **MAE of 0.26**, an **RMSE of 0.57**, and an **R² score of 0.9978**. Feature importance analysis identified the **Froude number (`Fr`)** as the dominant predictor.

Overall, the results demonstrate the effectiveness of Gradient Boosting for this structured nonlinear regression problem. Because the dataset is relatively small, the reported results represent performance on the selected train-test split, and cross-validation would be a useful extension for assessing model stability and generalization.
