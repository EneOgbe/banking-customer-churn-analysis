# Banking Customer Churn Analysis & Prediction

## Project Overview
This project analyses customer churn behaviour and builds a predictive machine learning model using simulated retail banking data, completed as part of the Lloyds Banking Group Data Science job simulation.

The objective is to identify customers at risk of churn and uncover the key behavioural drivers behind churn in order to inform data-driven retention strategies.

The project follows an end-to-end data science workflow, from exploratory data analysis (EDA) and preprocessing through to model development, evaluation, and business interpretation.

---

## Business Context
Customer churn represents a significant risk to retail banks, particularly among digitally active customers and small business owners.  
Understanding *why* customers leave is just as important as predicting *who* is likely to leave.

This project focuses on:
- Digital engagement patterns
- Spending behaviour
- Customer service interactions
- Demographic context

The final output is an interpretable model that supports actionable business decisions rather than maximising accuracy alone.

---

## Data Description
The dataset consists of simulated customer-level banking data split across multiple sources:

- **Customer Demographics**: age, gender, marital status, income level  
- **Transaction History**: transaction count, total spend, average spend  
- **Customer Service Interactions**: total interactions, unresolved issues  
- **Online Activity**: login frequency and service usage  
- **Target Variable**: churn status (0 = retained, 1 = churned)

All data sources were merged into a single analytical dataset at customer level.

---

## Project Structure
banking-customer-churn-analysis/
│
├── data/
│ └── raw/
│ └── Customer_Churn_Data_Large.xlsx
│
├── notebooks/
│ ├── 01_eda_customer_churn.ipynb
│ └── 02_model_customer_churn.ipynb
│
├── reports/
│ ├── Customer_Churn_Task1_Final_Report.pdf
│ └── Customer_Churn_Task2_Business_Report.pdf
│
├── .gitignore
├── README.md



---

## Task 1: Exploratory Data Analysis & Preprocessing
### Key Activities
- Descriptive statistics (mean, median, variance, min/max)
- Churn rate analysis
- Behavioural comparisons between churned and retained customers
- Visualisations including:
  - Churn by age group
  - Login frequency vs churn
  - Customer service issues vs churn
  - Transaction behaviour vs churn
- Data cleaning and preprocessing:
  - Missing value handling
  - Feature aggregation
  - Categorical encoding
  - Feature scaling
  - Dataset preparation for modelling

### Key Insights
- Churn rate ≈ 20%
- Lower login frequency is associated with higher churn
- Spending behaviour is more informative than transaction volume
- Customer service friction contributes to churn risk
- Behavioural features outweigh demographic ones

A detailed Task 1 report is included in the `reports/` folder.

---

## Task 2: Predictive Modelling
### Models Evaluated
1. **Logistic Regression (Baseline)**
   - High interpretability
   - Limited predictive power (ROC-AUC ≈ 0.52)

2. **Random Forest (Final Model)**
   - Captures non-linear relationships
   - Improved cross-validation performance (ROC-AUC ≈ 0.56)
   - Selected as the final model

### Evaluation Metrics
- Stratified train/test split
- Cross-validation ROC-AUC
- Confusion matrix
- Precision, recall, F1-score
- ROC curve analysis

### Key Results
- Churn behaviour is weakly separable using available features
- Model recall for churners is limited, reflecting realistic early-stage churn modelling
- Results highlight the need for richer temporal and behavioural data

---

## Key Drivers of Churn
Feature importance analysis from the Random Forest model identified:

1. **Login Frequency** – strongest indicator of churn risk  
2. **Spending Behaviour** – average and total spend  
3. **Age** – moderate influence  
4. **Transaction Count** – weaker than monetary value  
5. **Customer Service Issues** – unresolved interactions increase churn risk  
6. **Demographics** – limited predictive impact

---

## Business Recommendations
- Monitor digital disengagement as an early churn signal
- Trigger proactive outreach for customers with declining login activity
- Target customers with reduced spending using personalised offers
- Prioritise resolution of customer service issues
- Use the model as a *risk triage tool* rather than a definitive decision engine

---

## Limitations & Future Improvements
- Limited temporal depth of behavioural data
- Aggregated features reduce predictive resolution
- Potential improvements include:
  - Time-series features
  - Product-level engagement metrics
  - Longer observation windows
  - Cost-sensitive classification thresholds

---

## Tools & Technologies
- Python
- pandas, numpy
- matplotlib
- scikit-learn
- Jupyter Notebook

---

## Author
**Ene Ogbe**  
Data Analytics & Data Science Portfolio Project  
