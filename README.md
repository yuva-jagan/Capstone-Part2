# Part 2 – Machine Learning Models and Evaluation

## Introduction

In this part of the project, I prepared the cleaned dataset for machine learning, built regression and classification models, evaluated their performance, and compared the results using different evaluation metrics.

## Dataset

The project uses the Medical Cost Personal Dataset. The cleaned dataset generated in Part 1 was used for model building. If the dataset is not available in this repository, it can be downloaded from a publicly available source such as Kaggle.

## Data Preprocessing

The cleaned dataset was loaded into a pandas DataFrame. The target variable for regression was the insurance charges column.

For the classification task, a new binary target variable was created by comparing the insurance charges with the median value. Records with charges greater than the median were assigned to one class, while the remaining records were assigned to the other class.

Categorical variables were converted into numerical values using one-hot encoding. The dataset was then divided into training and testing sets using train_test_split(). Finally, StandardScaler was used to standardize the feature values before training the classification models.

## Regression Models

Two regression models were trained.

### Linear Regression

A Linear Regression model was trained to predict insurance charges. The model performance was evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² Score.

### Ridge Regression

A Ridge Regression model was trained to reduce overfitting by adding L2 regularization. The same evaluation metrics were calculated and compared with the Linear Regression model.

## Classification Model

A Logistic Regression model was trained to classify whether insurance charges were above or below the median value.

The predicted probabilities were used to generate ROC curves and calculate the Area Under the Curve (AUC).

## Model Evaluation

The following evaluation metrics were calculated during model evaluation.

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC Score
- Confusion Matrix

ROC curves were generated to visualize the classification performance.

## Threshold Comparison

Two Logistic Regression models with different regularization strengths were compared.

- Logistic Regression (C = 1.0)
- Logistic Regression (C = 0.01)

The precision, recall, and ROC-AUC values were compared to understand the effect of changing the regularization parameter.

## Bootstrap Confidence Interval

Bootstrap sampling was performed to estimate the confidence interval for the difference in AUC scores between the two Logistic Regression models.

The calculated confidence interval showed that the difference in performance between the two models was very small.

## Results

The Logistic Regression models achieved high ROC-AUC scores, showing good classification performance.

The comparison between different values of C indicated that changing the regularization strength had only a small effect on the overall model performance.

The regression models were also evaluated successfully using standard regression metrics.

## Conclusion

The preprocessing steps prepared the dataset successfully for machine learning. Both regression and classification models performed well on the dataset. Logistic Regression achieved strong classification performance, while Ridge Regression helped control overfitting without significantly reducing prediction accuracy.

The evaluation metrics and ROC curves provided a clear understanding of model performance and will be used as a baseline for the advanced ensemble models developed in Part 3.

## Repository Contents

This repository contains:

- `part2.ipynb` – Notebook containing preprocessing, model training, and evaluation code.
- `cleaned_data.csv` – Cleaned dataset used for model training.
- `README.md` – Documentation for Part 2.

## Results

The following results were obtained during model evaluation.

| Model | Precision | Recall | ROC-AUC |
|-------|-----------|--------|---------|
| Logistic Regression (C = 1.0) | 0.894366 | 0.933824 | 0.966355 |
| Logistic Regression (C = 0.01) | 0.906475 | 0.926471 | 0.965575 |

Bootstrap analysis was performed to compare the AUC scores of the two Logistic Regression models.

- Mean AUC Difference: **0.000819**
- 95% Confidence Interval: **[-0.001228, 0.003092]**

The confidence interval includes zero, which indicates that the difference in performance between the two Logistic Regression models is very small. Both models achieved excellent classification performance.