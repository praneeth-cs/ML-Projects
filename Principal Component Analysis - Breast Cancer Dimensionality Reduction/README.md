# Principal Component Analysis - Breast Cancer Dimensionality Reduction

## Project Overview

This project applies **Principal Component Analysis (PCA)** to the Breast Cancer Wisconsin (Diagnostic) dataset to reduce the dimensionality of 30 numerical diagnostic features.

The project analyzes explained variance, visualizes the data in PCA space, examines principal-component loadings, and compares Logistic Regression performance using the original features and PCA-reduced features.

The main objective is to determine whether PCA can substantially reduce the feature space while retaining most of the dataset's information and maintaining strong classification performance.

---

## Dataset

The dataset contains **569 observations** and **30 numerical diagnostic features** describing characteristics of breast cell nuclei.

The target variable is `diagnosis`:

- `M` — Malignant
- `B` — Benign

The `id` identifier and the empty `Unnamed: 32` column are removed before analysis.

Dataset source: **Breast Cancer Wisconsin (Diagnostic) Data — Kaggle**

https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data

---

## Project Workflow

1. Import Required Libraries
2. Load Dataset
3. Explore Dataset
4. Missing Values and Duplicates
5. Data Cleaning
6. Exploratory Data Analysis
7. Prepare Features and Target
8. Standardize Features
9. Apply PCA to All Components
10. Explained Variance Analysis
11. Components Required for Target Variance
12. Two-Dimensional PCA Visualization
13. Principal Component Loadings
14. Visualize Principal Component Loadings
15. Classification Comparison: Original Features vs PCA
    - 15.1 Train-Test Split
    - 15.2 Logistic Regression Using Original Features
    - 15.3 Logistic Regression Using PCA Features
16. Model Performance Comparison
17. Confusion Matrices
18. Key Findings
19. Conclusion

---

## Data Preprocessing

The `id` column is removed because it is an identifier rather than a meaningful diagnostic feature. The completely empty `Unnamed: 32` column is also removed.

No duplicate rows were found.

Before PCA, all 30 diagnostic features are standardized using **StandardScaler** because PCA is sensitive to differences in feature scale.

---

## PCA Results

PCA substantially reduced the feature space while preserving most of the dataset's variance.

| Variance Retained | Components Required |
|---|---:|
| 90% | 7 |
| 95% | 10 |
| 99% | 17 |

Using **10 principal components** retained approximately **95.21% of the variance**, reducing the feature space from 30 dimensions to 10.

This represents a **66.67% reduction in dimensionality**.

The first two principal components explained approximately **63.24%** of the total variance.

---

## Principal Component Loadings

PC1 was influenced strongly by features related to:

- Concave points
- Concavity
- Compactness
- Perimeter
- Radius
- Area

PC2 was influenced strongly by **fractal-dimension features**, along with several size and compactness-related measurements.

The loading analysis demonstrates how PCA combines information from correlated original variables into a smaller set of orthogonal components.

---

## Model Performance Comparison

Logistic Regression was used to evaluate whether the PCA-reduced representation retained useful predictive information.

| Model | Number of Features | Accuracy |
|---|---:|---:|
| Logistic Regression - Original Features | 30 | 96.49% |
| Logistic Regression - PCA Features | 10 | **97.37%** |

The PCA-based model used only one-third of the original dimensions while achieving slightly higher test accuracy in this experiment.

---

## Key Findings

- The cleaned dataset contained **569 observations** and **30 numerical diagnostic features**.
- **7 components** preserved at least 90% of the total variance.
- **10 components** preserved approximately **95.21% of the variance**.
- **17 components** were required to preserve at least 99% of the variance.
- Reducing 30 original features to 10 principal components resulted in a **66.67% reduction in dimensionality**.
- The first two principal components explained approximately **63.24%** of the total variance.
- PC1 was influenced strongly by tumor concavity, concave points, compactness, perimeter, radius, and area measurements.
- PC2 was influenced strongly by fractal-dimension features and several size and compactness-related measurements.
- Logistic Regression achieved **96.49% accuracy** using the original standardized features.
- Logistic Regression achieved **97.37% accuracy** using the PCA-reduced features.
- PCA substantially reduced the feature space while maintaining strong predictive performance.

---

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## Project Structure

```text
Principal Component Analysis - Breast Cancer Dimensionality Reduction/
│
├── breast_cancer.csv
├── principal_component_analysis_breast_cancer_dimensionality_reduction.ipynb
├── README.md
└── requirements.txt
```

---

## Conclusion

This project demonstrated that **Principal Component Analysis (PCA)** can substantially reduce the dimensionality of the Breast Cancer Wisconsin Diagnostic dataset while preserving most of its information.

PCA reduced the original **30 features to 10 principal components** while retaining approximately **95.21% of the total variance**, corresponding to a **66.67% reduction in dimensionality**.

Logistic Regression achieved **96.49% accuracy** using the original standardized features and **97.37% accuracy** using the PCA-reduced features.

Overall, PCA produced a significantly more compact feature representation without sacrificing classification performance, demonstrating its usefulness for dimensionality reduction, visualization, and handling correlated numerical features.
