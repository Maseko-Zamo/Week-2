# Week-2 - Loan Prediction Model
# Feature Engineering

# AnalystLab Africa – Week 2: Data Preprocessing & Feature Engineering

## Overview

This project covers Week 2 of my AnalystLab Africa Data Science Internship, focusing on preparing a loan dataset for machine learning.

The main goal was to clean the data, transform features, identify outliers, scale numerical variables, and select useful features for a future loan eligibility prediction model.

## Objectives

- Clean and prepare the dataset
- Handle missing values
- Encode categorical variables
- Detect and manage outliers
- Apply feature scaling
- Analyse correlations
- Select relevant features for machine learning

## Tools & Technologies

- Python
- Pandas – data manipulation and analysis
- NumPy – numerical operations
- Matplotlib – data visualisation and boxplots
- Scikit-learn – encoding and feature scaling
- Jupyter Notebook – development environment

## Data Preprocessing

### Missing Values

Missing values were identified in several variables:

- Gender – 13
- Married – 3
- Dependents – 15
- Self Employed – 32
- Loan Amount – 22
- Loan Amount Term – 14
- Credit History – 50

Mode imputation was used for most variables, while the median was used for Loan Amount.

No duplicate records were identified.

## Feature Engineering

Several variables were renamed to make them clearer for modelling:

- `Loan_Amount_Term` → `LoanDurationMonths`
- `Credit_History` → `Credit_Score`
- `Property_Area` → `Area_Type`
- `Education` → `Graduated`

The `Loan_ID` column was removed because it had no predictive relevance.

## Feature Encoding

Categorical variables were converted into numerical form using:

- Label Encoding – Gender, Married, Self Employed, Graduated and Loan Status
- One-Hot Encoding – Area Type

This made the categorical variables suitable for machine learning algorithms.

## Outlier Detection

Boxplots were used to identify unusual observations.

Outliers were particularly noticeable in:

- Applicant Income
- Coapplicant Income
- Total Income
- Loan Amount
- Loan Income Ratio

The IQR method was selected for handling outliers.

## Feature Scaling

Different scaling approaches were considered based on the characteristics of the variables.

### RobustScaler

RobustScaler was used for variables affected by outliers, including:

- Applicant Income
- Coapplicant Income
- Loan Amount
- Total Income
- Loan Income Ratio

### StandardScaler

StandardScaler was used for:

- Loan Duration Months

## Correlation & Feature Selection

A correlation analysis and heatmap were used to understand the relationships between the features and `Loan_Status`.

The strongest identified relationships with Loan Status were:

| Feature | Correlation |
|---|---:|
| Credit Score | 0.540 |
| Area Type – Semiurban | 0.136 |
| Married | 0.096 |
| Gender | 0.018 |
| Coapplicant Income | 0.012 |
| Dependents | 0.010 |

Credit Score had the strongest correlation with Loan Status.

Although Applicant Income and Coapplicant Income had weaker correlations, income variables were retained because they are relevant to the business decision of assessing loan eligibility.

`TotalIncome` was identified as redundant because it is derived from the income variables, so it was selected for removal.

## Key Findings

1. Credit Score was the strongest feature associated with Loan Status, with a correlation of 0.540.
2. Area Type – Semiurban showed a positive but relatively weak correlation of 0.136.
3. Several numerical variables contained significant outliers, particularly income-related variables and Loan Amount.
4. Missing values required different treatment depending on the type of variable.
5. Categorical variables needed encoding before being used for machine learning.
6. Scaling was important because the numerical features had different ranges and some contained substantial outliers.
7. Feature selection should consider both statistical relationships and business relevance, rather than relying only on correlation.
8. TotalIncome was removed because it duplicated information already represented by the income variables.

## What I Learned

This week strengthened my understanding of how important data preprocessing and feature engineering are before building a machine learning model.

I learned that preparing data involves more than simply removing missing values. It also requires appropriate encoding, treatment of outliers, scaling, meaningful feature names, and careful feature selection.

## Project Outcome

The processed dataset is being prepared for the next stage of the project: developing and evaluating a machine learning model for loan eligibility prediction.


**AnalystLab Africa Data Science Internship – Week 2**

**Focus:** Data Cleaning | Feature Engineering | Outlier Detection | Feature Scaling | Correlation | Feature Selection
