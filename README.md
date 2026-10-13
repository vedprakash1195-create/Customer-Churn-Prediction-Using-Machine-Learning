# Customer-Churn-Prediction-Using-Machine-Learning
Customer Churn Prediction
# Customer Churn Prediction Using Machine Learning

A machine learning classification project to predict customer churn using the IBM Telco Customer Churn dataset.

## Overview

Customer churn occurs when customers stop using a company's services. Predicting churn can help businesses identify at-risk customers and plan customer retention campaigns.

This project compares Logistic Regression, Decision Tree, and Random Forest classifiers to predict whether a telecom customer is likely to churn.

## Objectives

- Clean and prepare customer data.
- Explore customer churn patterns.
- Build and compare classification models.
- Identify important churn-related features.
- Evaluate precision, recall, F1 score, ROC-AUC, and confusion matrix.
- Explore decision thresholds for churn prediction.

## Dataset

**Dataset:** IBM Telco Customer Churn

The dataset includes customer demographics, subscribed services, contract details, tenure, charges, payment methods, and the target variable `Churn`.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Workflow

1. Load the dataset.
2. Clean data and convert `TotalCharges` to numeric.
3. Handle missing values.
4. Remove `customerID` from predictive features.
5. Perform exploratory data analysis.
6. Split data using stratified sampling.
7. Apply numerical scaling and categorical one-hot encoding.
8. Train Logistic Regression, Decision Tree, and Random Forest.
9. Compare model performance.
10. Examine feature coefficients and feature importance.
11. Evaluate a classification threshold using validation data.
12. Assess predictions using a confusion matrix.

## Model Results

Initial comparison after removing `customerID`:

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 73.8% | 50.4% | 78.3% | 61.4% | 0.841 |
| Decision Tree | 74.1% | 50.8% | 79.1% | 61.9% | 0.829 |
| Random Forest | 78.3% | 61.8% | 47.6% | 53.8% | 0.822 |

### Threshold Evaluation

For the Decision Tree threshold evaluation, a threshold of 0.50 produced these test results:

| Metric | Result |
|---|---:|
| Accuracy | 73.2% |
| Precision | 49.7% |
| Recall | 77.3% |
| F1 Score | 60.5% |

Confusion matrix:

```text
[[742, 293],
 [85, 289]]
```

The threshold evaluation used a separately fitted model. Therefore, its metrics should not be interpreted as a direct improvement or decline versus the initial Decision Tree model comparison.

## Key Insights

- Tenure was an important feature in the Logistic Regression model.
- Contract type was associated with churn predictions.
- Month-to-month contracts and fiber-optic service had positive coefficients in the fitted Logistic Regression model.
- The Decision Tree identified a larger proportion of churners than Random Forest in the initial comparison.

## How to Run

1. Clone or download this repository.
2. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

3. Place the dataset CSV file in the project directory.
4. Open the notebook in Jupyter.
5. Run the notebook cells in order.

## Future Improvements

- Compare more thresholds using validation data.
- Tune model hyperparameters using cross-validation.
- Examine precision-recall curves.
- Evaluate the business cost of false positives and false negatives.
- Consider probability calibration and additional models.

## Disclaimer

This project is for learning and demonstration purposes. Model predictions are not guaranteed to identify future churn accurately, and the observed associations do not establish causation.
