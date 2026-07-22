# Gradient Boosting Classifier - Bank Marketing Prediction

## Project Overview

This project implements a **Gradient Boosting Classifier** to predict whether a bank client will subscribe to a term deposit.

The project evaluates a full-feature model, investigates the predictive influence of the `duration` feature, and addresses target-class imbalance using **SMOTENC oversampling**.

---

## Dataset

The Bank Marketing dataset contains **45,211 observations** and **17 columns**. The target variable is `y`:

- `no` — client did not subscribe
- `yes` — client subscribed to a term deposit

The target is highly imbalanced, with substantially fewer `yes` observations than `no` observations.

Dataset source: **UCI Machine Learning Repository — Bank Marketing**

https://archive.ics.uci.edu/dataset/222/bank+marketing

---

## Project Workflow

1. Import Required Libraries
2. Load Dataset
3. Explore Dataset
4. Missing Values and Duplicates
5. Target Distribution
6. Exploratory Data Analysis
7. Prepare Features and Target
8. Identify Numerical and Categorical Features
9. Train-Test Split
10. Preprocessing Pipeline
11. Train Gradient Boosting Classifier
12. Make Predictions
13. Model Evaluation
14. Confusion Matrix
15. ROC Curve
16. Feature Importance
17. Duration Feature Analysis
18. Model Comparison
19. Class Imbalance Analysis
20. Final Model Comparison
21. Key Findings
22. Conclusion

---

## Data Preprocessing

The target is encoded as `0` for `no` and `1` for `yes`. Numerical features are passed directly to the model, while categorical features are transformed using **One-Hot Encoding**.

A stratified train-test split preserves the target distribution. For the imbalance experiment, **SMOTENC** is applied only to the training data so the test set remains representative of the original distribution.

---

## Model

The primary algorithm is **Gradient Boosting Classifier**, using 100 estimators, a learning rate of 0.1, maximum tree depth of 3, and a fixed random state.

Three experiments are compared:

1. Full-feature model
2. Duration-free model
3. Duration-free model with SMOTENC oversampling

---

## Duration Feature Analysis

The full-feature model performed strongly, but `duration` accounted for approximately **46.97% of feature importance**.

Because call duration is only known after a marketing call occurs, it cannot be used for genuine pre-call prediction. A second model was therefore trained without `duration`.

---

## Final Model Comparison

| Model | Accuracy | ROC-AUC | Yes Precision | Yes Recall | Yes F1 |
|---|---:|---:|---:|---:|---:|
| Full-Feature Model | **90.55%** | **0.9240** | 65.26% | 41.02% | **50.38%** |
| Duration-Free Model | 89.43% | 0.8021 | **65.94%** | 19.94% | 30.62% |
| Duration-Free + SMOTENC | 75.85% | 0.7704 | 26.95% | **62.19%** | 37.60% |

SMOTENC substantially increased the model's ability to identify subscribers, but produced more false positives and lower overall accuracy.

---

## Key Findings

- The full-feature model achieved **90.55% accuracy** and **0.9240 ROC-AUC**.
- `duration` was the dominant feature at approximately **46.97% feature importance**.
- Removing `duration` created a more realistic pre-call model but reduced `Yes` recall from **41.02% to 19.94%**.
- The target is strongly imbalanced, making accuracy alone an insufficient evaluation metric.
- SMOTENC increased `Yes` recall from **19.94% to 62.19%**.
- Positive-class F1 improved from **30.62% to 37.60%** after oversampling.
- The recall improvement came with lower `Yes` precision (**65.94% → 26.95%**) and lower accuracy (**89.43% → 75.85%**).
- The experiment demonstrates the **precision-recall trade-off** involved in handling imbalanced classification data.

---

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- imbalanced-learn
- Jupyter Notebook

---

## Project Structure

```text
Gradient Boosting Classifier - Bank Marketing Prediction/
│
├── bank_marketing.csv
├── gradient_boosting_classifier_bank_marketing_prediction.ipynb
├── README.md
└── requirements.txt
```

---

## Conclusion

This project demonstrated **Gradient Boosting Classification** for term-deposit prediction while highlighting feature availability and class imbalance.

The full-feature model achieved **90.55% accuracy** and **0.9240 ROC-AUC**, but depended heavily on `duration`, which is unavailable before contacting a client. Removing it produced a more realistic pre-call model but reduced positive-class recall to **19.94%**.

Applying SMOTENC increased subscriber recall substantially to **62.19%** and improved positive-class F1, although precision and overall accuracy decreased.

Overall, the results show that model performance must be evaluated according to the prediction objective. The duration-free model produces more precise positive predictions, while the SMOTENC model identifies a much larger proportion of potential subscribers. The project also demonstrates why accuracy alone is insufficient for imbalanced classification problems.
