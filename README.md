# Customer Churn Prediction Benchmark

Machine Learning benchmark project for customer churn prediction using multiple classification algorithms, feature engineering, model evaluation, and ensemble learning.

---

## Project Overview

This project aims to predict whether a customer will churn using behavioral and subscription-related customer information.

The objective was not only maximizing accuracy but understanding:

- Data quality
- Feature importance
- Distribution shift
- Generalization ability
- Model comparison
- Ensemble performance

Dataset contains customer demographic information, engagement metrics, subscription details, and churn labels.

---

## Problem Statement

Customer churn directly impacts business revenue.

The goal:

Predict:

Target Variable:

```

Churn

```

Values:

- 0 → Customer retained
- 1 → Customer churned

---

## Dataset Information

Training Dataset Size:

```

440,833 rows
12 columns

```

Features:

| Feature | Description |
|----------|-------------|
| CustomerID | Unique customer identifier |
| Age | Customer age |
| Gender | Male/Female |
| Tenure | Customer relationship duration |
| Usage Frequency | Product/service usage |
| Support Calls | Number of support interactions |
| Payment Delay | Delay in payments |
| Subscription Type | Premium / Standard / Basic |
| Contract Length | Monthly / Quarterly / Annual |
| Total Spend | Customer spending |
| Last Interaction | Recency information |
| Churn | Target variable |

---

## Project Workflow

### 1. Data Loading

Libraries used:

```python
pandas
numpy
matplotlib
seaborn
scikit-learn
```

Dataset imported:

```python
train.csv
test.csv
```

---

### 2. Exploratory Data Analysis (EDA)

Performed:

- Shape analysis
- Feature inspection
- Missing value detection
- Duplicate checking
- Statistical summary
- Correlation heatmap
- Distribution visualization

Example:

```python
df.shape
df.describe()
df.isnull().sum()
df.duplicated()
```

---

### 3. Data Cleaning

Operations performed:

#### Missing Value Handling

```python
df.dropna()
```

#### Duplicate Validation

Checked duplicate entries.

#### Categorical Encoding

Applied encoding for:

- Gender
- Subscription Type
- Contract Length

---

### 4. Feature Engineering

Created engineered features:

#### Spend Per Tenure

```

Spend_Per_Tenure =
Total Spend / Tenure

```

Purpose:

Measure customer value generation speed.

---

#### Support To Usage Ratio

```

Support_to_Usage =
Support Calls / Usage Frequency

```

Purpose:

Estimate customer dissatisfaction.

---

### 5. Distribution Shift Detection

Train and test distributions compared.

Observed differences:

- Age
- Payment Delay
- Total Spend
- Support Calls

Finding:

Independent test data distribution differed from training distribution.

Generalization became harder.

---

### 6. Models Used

### Logistic Regression

Strengths:

- Fast
- Interpretable
- Good baseline

---

### Gaussian Naive Bayes

Strengths:

- Simple
- Fast inference
- Strong generalization

---

### K Nearest Neighbors

Strengths:

- Non-parametric
- Local pattern learning

---

### Stacking Ensemble

Base Models:

```python
GaussianNB
LogisticRegression
KNN
```

Meta Learner:

```python
LogisticRegression
```

Purpose:

Combine strengths of multiple algorithms.

---

## Evaluation Metrics

Used:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Classification Report

Example:

```python
accuracy_score()
precision_score()
recall_score()
f1_score()
confusion_matrix()
classification_report()
```

---

## Results Summary

Observed behavior:

Cross validation produced strong scores.

Independent test evaluation exposed distribution shift.

Naive Bayes generalized best.

Stacking ensemble improved stability but did not completely overcome train-test mismatch.

Key insight:

Higher validation score does not guarantee real-world performance.

Generalization matters more than leaderboard numbers.

---

## Challenges Faced

### Distribution Shift

Train and test distributions differed.

### Model Generalization

Models overfit validation assumptions.

### Notebook Recovery

Notebook corruption and Git recovery workflow handled during development.

---

## Tech Stack

Python

Libraries:

```text
Pandas
NumPy
Scikit Learn
Matplotlib
Seaborn
```

Development Environment:

```text
VS Code
Jupyter Notebook
Git
GitHub
```

---

## Repository Structure

```

project/

│

├── train.csv
├── test.csv
├── project.ipynb
├── README.md

```

---

## Future Improvements

- XGBoost
- LightGBM
- CatBoost
- Hyperparameter optimization
- SHAP explainability
- ROC-AUC optimization
- Calibration techniques
- Better feature engineering

---

## Learning Outcomes

This project improved understanding of:

- EDA
- Data preprocessing
- Feature engineering
- Classification algorithms
- Model benchmarking
- Distribution shift
- Ensemble learning
- Git workflow
- Debugging notebook issues

---

## Author

Krishna

Machine Learning Engineering Journey

Focused on:

- ML systems
- Open source
- Applied AI
- Model evaluation

---

## Final Conclusion

This project demonstrates that machine learning performance is not only about maximizing accuracy.

Understanding data quality, feature behavior, and model generalization is equally critical.

Real ML engineering begins when models fail unexpectedly and investigation starts.
