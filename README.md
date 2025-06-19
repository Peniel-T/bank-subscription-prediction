Bank Subscription Prediction

This project analyzes a direct marketing campaign dataset from a Portuguese banking institution to predict whether a client will subscribe to a term deposit. It covers exploratory data analysis (EDA), feature engineering, and supervised machine learning models including Logistic Regression, Random Forest, and XGBoost.

---

 Dataset Overview

The dataset includes client information such as:
- Demographics: `age`, `job`, `marital`, `education`
- Financial behavior: `housing`, `loan`, `default`
- Marketing interaction: `contact`, `month`, `campaign`, `pdays`
- Economic indicators: `emp.var.rate`, `euribor3m`, `nr.employed`, etc.
- Target variable: `y` (whether a client subscribed to a term deposit)

---

Steps Performed

1. **Exploratory Data Analysis (EDA)**
   - Analyzed categorical and numerical distributions
   - Identified imbalances in the target variable
   - Visualized relationships across age, education, marital status

2. **Data Preprocessing**
   - Removed entries with `unknown` values
   - Handled outliers using IQR capping
   - Created new features like `age cluster` and `marital_edu`

3. **Feature Engineering**
   - Mapped categorical variables using One-Hot Encoding
   - Dropped `duration` (leakage risk)
   - Converted target `y` to binary: `yes` = 1, `no` = 0

4. **Model Building & Evaluation**
   - Logistic Regression
   - Random Forest Classifier
   - XGBoost with hyperparameter tuning using GridSearchCV


Model Performance Summary

### Logistic Regression:
- Accuracy: 89%
- Precision (Class 1): 0.62
- Recall (Class 1): 0.25
- F1-score (Class 1): 0.35

### Random Forest:
- Accuracy: 87%
- Precision (Class 1): 0.49
- Recall (Class 1): 0.30
- F1-score (Class 1): 0.37

### XGBoost (Best Model):
- Accuracy: 88%
- Precision (Class 1): 0.53
- Recall (Class 1): 0.30
- F1-score (Class 1): 0.38
- **Best Parameters:** `max_depth=7`, `n_estimators=200`, `learning_rate=0.2`



 Insights & Recommendations

- Most subscribers fall within age 30–45, often professionals with higher education.
- Imbalanced classes: Majority of customers do **not** subscribe, making metrics like F1-score and recall crucial.
- Economic indicators like `euribor3m` and `emp.var.rate` showed strong influence on predictions.
- Future improvement: Try SMOTE or ensemble methods to handle class imbalance better.
