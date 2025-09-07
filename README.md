# Telco Customer Churn Analysis

## Introduction

This project focuses on analyzing customer churn in the telecom sector. Customer churn represents the proportion of customers who discontinue their subscription during a given period. The primary objectives of this project are:

1. To explore the dataset and identify key factors associated with customer churn.
2. To build predictive models that can classify whether a customer is likely to churn.
3. To evaluate the performance of different machine learning models and finalize the best one for deployment.

---

## Dataset Description

* **Source**: Telco Customer Churn dataset
* **Records**: 7,043 rows
* **Features**: 21 columns
* **Target Variable**: `Churn` (Yes = 1, No = 0)

---

## Methodology

### 1. Data Preprocessing & Cleaning

* Converted `TotalCharges` to numeric values.
* Removed 11 records with missing values (\~0.15% of data).
* Created `tenure_group` feature to categorize customers based on service duration.
* Dropped irrelevant features such as `customerID`.

### 2. Exploratory Data Analysis (EDA)

* Churn rate: **26.5%** (imbalanced).
* Key observations:

  * Higher churn among month-to-month contract customers.
  * Customers without tech support or online security are more likely to churn.
  * Electronic check payment method shows the highest churn.
  * Short tenure + high monthly charges → higher churn probability.

### 3. Model Building

* **Train/Test split**: 80/20.
* **Algorithms Tested**:

  * Decision Tree (Accuracy: \~78%) – poor recall for churn class.
  * Random Forest (Accuracy: \~80%) – better than Decision Tree.
* **Class Imbalance Handling**: Applied **SMOTEENN** (oversampling + undersampling).
* **Final Model**: Random Forest with SMOTEENN.

### 4. Evaluation Metrics

* Final model achieved:

  * **Accuracy**: 94%
  * **Precision (Churn=1)**: 0.94
  * **Recall (Churn=1)**: 0.96
  * **F1-score (Churn=1)**: 0.95

### 5. Model Deployment

* Best model saved as `model.sav` (Random Forest with SMOTEENN).
* Ready for API integration and deployment in production.

---

## Tools & Libraries

* **Languages**: Python
* **Libraries**: Pandas, Numpy, Seaborn, Matplotlib, Scikit-learn, Imbalanced-learn, Pickle

---

## Conclusion

The project successfully identified important factors leading to customer churn and developed a predictive model with strong performance metrics. The Random Forest model with SMOTEENN proved to be the most effective.

