# Customer Churn Prediction

## Project Overview

This project focuses on predicting customer churn using machine learning.

The goal is to predict whether a customer is likely to leave a telecommunications company based on their demographic information, services, contract type, tenure, and billing information.

The project demonstrates a complete machine learning workflow, from data exploration and preprocessing to model training and evaluation.

## Dataset

The project uses the **Telco Customer Churn** dataset.

* 7,043 original customer records
* Target variable: `Churn`
* `Yes` — customer left the company
* `No` — customer remained

After data cleaning, the dataset contains **7,010 records and 20 columns**.

## Project Structure

```text
Customer-Churn-Prediction/
│
├── data/
│   ├── WA_Fn-UseC_-Telco-Customer-Churn.csv
│   └── WA_Fn-UseC_cleaned_Telco-Customer-Churn
│
├── notebooks/
│   ├── 01_Data_Exploration.ipynb
│   └── 02_Preprocessing_and_Modeling.ipynb
│
├── README.md
└── requirements.txt
```

## Data Exploration and Cleaning

The following steps were performed:

* Inspected dataset structure and data types
* Checked missing values
* Removed 11 records with missing `TotalCharges`
* Removed `customerID` because it does not provide predictive information
* Removed 22 duplicate records after removing the identifier
* Analyzed numerical and categorical features
* Investigated relationships between customer characteristics and churn

### Key EDA Findings

* 26.5% of customers in the cleaned dataset churned.
* Month-to-month customers had the highest churn rate.
* Churned customers had lower average tenure.
* Churned customers had higher average monthly charges.
* `tenure` and `TotalCharges` had a strong positive correlation (0.83).

## Machine Learning

### Preprocessing

The dataset was divided into training and testing sets using an 80/20 split.

Categorical features were transformed using **One-Hot Encoding**.

Numerical features were standardized using **StandardScaler**.

### Models

Two classification models were trained:

1. Logistic Regression
2. Random Forest

## Model Evaluation

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

Because the target variable is imbalanced, recall and F1-score for the `Yes` class were also considered.

### Results

| Model               | Accuracy | Precision | Recall | F1-score |
| ------------------- | -------: | --------: | -----: | -------: |
| Logistic Regression |    0.808 |     0.670 |  0.542 |    0.599 |
| Random Forest       |    0.786 |     0.628 |  0.469 |    0.537 |

Logistic Regression achieved higher values across all evaluated metrics on the test set.

For the `Yes` class, Logistic Regression achieved a recall of **54.2%**, identifying 201 of 371 customers who actually churned.

## Technologies

* Python
* Pandas
* Scikit-learn
* Matplotlib
* Jupyter Notebook

## Conclusion

This project demonstrates an end-to-end customer churn prediction workflow, including data cleaning, exploratory data analysis, feature preprocessing, model training, and evaluation.

Among the two tested models, Logistic Regression achieved better performance on the test set and was able to identify more customers who actually churned.
