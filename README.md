# Advertising Sales — Model Comparison

A supervised-learning project in **R** comparing four approaches for predicting product sales from advertising expenditure.

## Objective

Predict `sales` from TV, radio, and newspaper advertising spend and compare model performance on the same held-out test set.

## Models

- Multiple linear regression
- Polynomial regression
- Regression tree
- Support vector regression (SVR)

## Methodology

The analysis uses a reproducible 70/30 train/test split. Model complexity is selected on the training data using cross-validation, and final performance is evaluated on the held-out test set using **RMSE, MAE, and R²**.

Key steps:

- exploratory data analysis;
- multiple linear regression as a baseline;
- cross-validation to select polynomial degree;
- cross-validation and pruning for the regression tree;
- hyperparameter tuning for polynomial-kernel SVR;
- out-of-sample comparison on a common test set;
- residual diagnostics for the best-performing model.

## Project structure

```text
.
├── advertising_model_comparison.ipynb
├── data/
│   └── Advertising.csv
└── README.md
```

## Requirements

The notebook uses an **R Jupyter kernel** and the following packages:

```r
install.packages(c("tidyverse", "boot", "tree", "e1071"))
```

## Running the project

Clone or download the repository, open the notebook from the repository root, and run the cells in order. The notebook first looks for the dataset at `data/Advertising.csv` and also supports `Advertising.csv` in the repository root.

## Notes

Because `sales` is a continuous target, the support-vector model is formulated as **support vector regression** rather than classification. Adjusted R² is not used as a common metric across all four model classes; final comparison is based on held-out predictive performance.
