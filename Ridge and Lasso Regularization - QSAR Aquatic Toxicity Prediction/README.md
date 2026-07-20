# Ridge and Lasso Regularization - QSAR Aquatic Toxicity Prediction

## Project Overview

This project demonstrates **Ridge (L2) and Lasso (L1) regularization** for predicting aquatic toxicity using the QSAR Aquatic Toxicity dataset.

The target variable is **LC50**, and the input variables consist of eight numerical molecular descriptors. Ordinary Linear Regression is included only as an **unregularized baseline** so that the effects of Ridge and Lasso regularization can be evaluated.

The project uses **RidgeCV** and **LassoCV** with 5-fold cross-validation to select regularization strength (`alpha`) from the training data.

## Dataset

The cleaned dataset contains:

- 546 observations
- 8 molecular descriptor features
- 1 continuous target variable: `LC50`
- 0 missing values

### Features

- `TPSA`
- `SAacc`
- `H050`
- `MLOGP`
- `RDCHI`
- `GATS1p`
- `nN`
- `C040`

### Target

- `LC50`

## Project Workflow

1. Load the cleaned dataset
2. Inspect dataset structure
3. Perform data-quality checks
4. Prepare the data
5. Conduct exploratory data analysis
6. Separate features and target
7. Create a train-test split
8. Standardize the input features
9. Train an unregularized Linear Regression baseline
10. Apply Ridge and Lasso regularization
11. Select alpha using 5-fold cross-validation
12. Evaluate predictive performance
13. Compare R² scores
14. Analyze actual vs predicted values
15. Analyze coefficient shrinkage
16. Examine Lasso feature selection

## Regularization Techniques

### Ridge Regularization

Ridge uses an **L2 penalty** that discourages large coefficient values. It generally retains all predictors while shrinking coefficient magnitudes.

### Lasso Regularization

Lasso uses an **L1 penalty** that can shrink selected coefficients exactly to zero. This allows Lasso to perform implicit feature selection in addition to controlling model complexity.

## Model Performance

| Approach | MAE | MSE | RMSE | R² Score |
|---|---:|---:|---:|---:|
| Linear Baseline | 0.9084 | 1.4615 | 1.2089 | 0.4743 |
| Ridge (L2 Regularization) | 0.9103 | 1.4563 | 1.2068 | 0.4761 |
| Lasso (L1 Regularization) | 0.9085 | 1.4495 | 1.2040 | 0.4786 |

Lasso achieved the highest R² score and lowest MSE and RMSE, although the differences between the three approaches were relatively small.

## Key Findings

- The unregularized Linear Regression baseline achieved an R² score of 0.4743.
- Ridge regularization slightly improved R² to 0.4761 and reduced MSE and RMSE compared with the baseline.
- Lasso regularization produced the highest R² score of 0.4786.
- Lasso also achieved the lowest MSE of 1.4495 and RMSE of 1.2040.
- The baseline produced a marginally lower MAE than Lasso, with values of 0.9084 and 0.9085 respectively.
- The small differences between the approaches indicate that regularization provided only a modest improvement in predictive performance on the held-out test set.
- RidgeCV and LassoCV used 5-fold cross-validation on the training data to select regularization strength rather than relying on manually chosen alpha values.
- The project demonstrates that the value of regularization is not limited to increasing R²; Ridge and Lasso also control coefficient magnitude, and Lasso can perform implicit feature selection.

## Conclusion

This project applied Ridge and Lasso regularization to a QSAR aquatic-toxicity prediction problem, using ordinary Linear Regression as an unregularized reference baseline.

Among the evaluated approaches, Lasso produced the best overall test-set performance, achieving an R² score of 0.4786 and the lowest MSE and RMSE. Ridge also produced a small improvement in R² and error metrics relative to the baseline. However, the performance differences were modest, indicating that regularization did not substantially change the predictive capability of the underlying linear model for this dataset.

The project nevertheless demonstrates the central purpose of regularization: controlling model complexity and coefficient magnitude rather than guaranteeing a large increase in predictive accuracy. Ridge provides L2-based coefficient shrinkage, while Lasso provides L1-based shrinkage with the additional possibility of eliminating less influential predictors. Cross-validated alpha selection makes the regularization process more systematic and reduces reliance on arbitrary hyperparameter choices.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Structure

```text
Ridge and Lasso Regularization - QSAR Aquatic Toxicity Prediction/
│
├── qsar_aquatic_toxicity_clean.csv
├── ridge_lasso_regularization_qsar_aquatic_toxicity.ipynb
├── README.md
└── requirements.txt
```
