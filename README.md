# Banking Customer Churn Analysis & Prediction

## Project Overview
This project explores customer churn behaviour and builds a predictive machine learning model using simulated retail banking data.  
The goal is to identify customers at risk of churn and understand the behavioural drivers behind churn in order to support data-driven retention strategies.

The project follows a complete data science workflow:
- Exploratory data analysis (EDA)
- Data cleaning and preprocessing
- Predictive modelling
- Model evaluation
- Business interpretation

---

## Business Context
Customer churn presents a significant challenge for retail banks, particularly in highly competitive digital banking environments.  
Understanding both **who is likely to churn** and **why customers churn** enables targeted retention actions and improved customer experience.

---

## 📁 Project Structure

```
banking-customer-churn-analysis/
│
├── data/
│   └── raw/
│       └── Customer_Churn_Data_Large.xlsx
│
├── notebooks/
│   └── customer_churn_analysis.ipynb
│
├── .gitignore
├── README.md

```

---

## Data Description
The dataset consists of simulated customer-level banking data combined from multiple sources:
- Customer demographics (age, gender, income level)
- Transaction behaviour (transaction count, total spend, average spend)
- Digital engagement (login frequency)
- Customer service interactions (total interactions, unresolved issues)
- Churn indicator (target variable)

All sources were merged into a single analytical dataset at customer level.

---

## Task 1: Exploratory Data Analysis & Preprocessing

### Key EDA Activities
- Descriptive statistics (mean, median, variance, min/max)
- Churn rate analysis
- Behavioural comparisons between churned and retained customers
- Visual analysis of:
  - Churn by age group
  - Login frequency vs churn
  - Transaction behaviour vs churn
  - Customer service interactions vs churn

### Key EDA Findings
- Overall churn rate ≈ **20%**
- Customers with **lower login frequency** show higher churn risk
- **Spending behaviour** is more informative than transaction volume
- Unresolved customer service issues increase churn likelihood
- Behavioural features are more predictive than demographic attributes

### Data Cleaning & Preprocessing
- Missing values handled through aggregation and validation checks
- Categorical variables encoded using one-hot encoding
- Numerical features scaled for modelling
- Features aggregated to customer-level for consistency
- Final dataset prepared for supervised learning

---

## Task 2: Predictive Modelling

### Model Selection
Two models were evaluated:

**Logistic Regression**
- Interpretable baseline model
- Limited predictive performance (ROC-AUC ≈ 0.52)

**Random Forest (Final Model)**
- Captures non-linear relationships
- Improved cross-validation performance (ROC-AUC ≈ 0.56)
- Selected as the final model due to better handling of behavioural patterns

### Model Training & Evaluation
- Stratified train-test split to preserve churn distribution
- Cross-validation for generalisation assessment
- Evaluation metrics:
  - ROC-AUC
  - Precision, Recall, F1-score
  - Confusion Matrix

### Model Performance Summary
- Test ROC-AUC ≈ **0.52**
- Churn recall ≈ **20%**
- Model is better suited as a **risk screening tool** rather than a definitive classifier

---

## Key Drivers of Customer Churn
Feature importance analysis from the Random Forest model identified:

1. **Login Frequency** – strongest churn signal (digital disengagement)
2. **Average & Total Spend** – declining spend increases churn risk
3. **Age** – moderate influence
4. **Transaction Count** – weaker than spending value
5. **Customer Service Interactions** – unresolved issues contribute to churn
6. **Demographics** – limited predictive impact

---

## Business Recommendations
- Monitor digital engagement as an early churn indicator
- Trigger proactive outreach for customers with declining activity
- Personalise offers for customers with reduced spending
- Prioritise resolution of customer service issues
- Use the model to **prioritise at-risk customers**, not as an absolute decision-maker

---

## Limitations & Future Improvements
- Limited temporal depth of behavioural data
- Aggregated features reduce predictive resolution
- Future improvements could include:
  - Time-series features
  - Product-level engagement metrics
  - Longer observation windows
  - Threshold optimisation for recall-focused retention strategies

---

## Tools & Technologies
- Python
- pandas, numpy
- scikit-learn
- matplotlib
- Jupyter Notebook

---

## Author
**Ene Ogbe**  
Data Science & Analytics Portfolio Project
