# Bank Marketing Analysis

## Overview
This project focuses on analyzing bank marketing data to predict whether a customer will subscribe to a bank's product. The dataset contains various features, including customer demographic information, contact details, and previous marketing interactions. The goal is to build a machine learning model that predicts customer responses and provides actionable insights for marketing strategies.

## Question: Bank Marketing Analysis
Attached is a txt file containing some real data that relates to a marketing campaign run by
a bank. The aim of the marketing campaign was to get customers to subscribe to a bank
term deposit product. Whether they did this or not is variable ‘y’ in the data set.

The bank in question is considering how to optimise this campaign in future.

**What would your recommendations to the marketing manager be?**

## Dataset
The dataset used in this analysis is a bank marketing dataset that includes the following key features:

Input variables: 1 - age (numeric) 2 - job : type of job (categorical: 'admin.','unknown','unemployed','management','housemaid','entrepreneur','student', 'blue-collar','self-employed','retired','technician','services') 3 - marital : marital status (categorical: 'married','divorced','single'; note: 'divorced' means divorced or widowed) 4 - education (categorical: 'unknown','secondary','primary','tertiary') 5 - default: has credit in default? (binary: 'yes','no') 6 - balance: average yearly balance, in euros (numeric) 7 - housing: has housing loan? (binary: 'yes','no') 8 - loan: has personal loan? (binary: 'yes','no') ### related with the last contact of the current campaign: 9 - contact: contact communication type (categorical: 'unknown','telephone','cellular') 10 - day: last contact day of the month (numeric) 11 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec') 12 - duration: last contact duration, in seconds (numeric) #### other attributes: 13 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact) 14 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric, -1 means client was not previously contacted) 15 - previous: number of contacts performed before this campaign and for this client (numeric) 16 - poutcome: outcome of the previous marketing campaign (categorical: 'unknown','other','failure','success')

Output variable (desired target): 17 - y - has the client subscribed a term deposit? (binary: 'yes','no')

## Data Analysis Process
During the data analysis, the following steps were taken:
1. **Data Distribution & Anomalies**: We analyzed the distribution of data, identified potential anomalies, and handled missing values.
2. **Data Processing**:
   - Categorical variables were converted to One-Hot Encoding format.
   - The pdays column was transformed into a binary variable was_contacted_before to indicate whether the customer was previously contacted.
   - We detected and handled multicollinearity by removing the poutcome_unknown feature, which had a strong negative correlation with was_contacted_before (100% correlation).
3. **Feature Correlation**: We analyzed feature correlations and identified that duration and poutcome_success were the most influential features on the target variable (whether the customer subscribes or not).

## Model Training & Evaluation
We used several machine learning models to predict customer subscriptions:
- **Random Forest Classifier**
- **Logistic Regression**
- **Support Vector Machine (SVM)**
- **Deep Neural Network (DNN)**

**All models were trained on unbalanced data, where 45% of customers subscribed.**

## Key Findings:
- **Best Model**: The **Random Forest Classifier** provided the best results with an accuracy of 60% in predicting customer subscriptions.
- **Data Balancing**: Balancing the dataset using **Undersampling** and **Oversampling** techniques improved accuracy **from 49% to 60%**.
- **Hyperparameter Optimization**: No significant improvement was observed in accuracy through hyperparameter optimization.

## Insights for Marketing Managers
Based on the analysis, we recommend the following actions:
1. Increase Call Duration: Longer conversations with customers are more likely to result in a subscription. duration is the most influential feature in predicting customer responses.
2. Monitor Customer Balance: Customers with low balances are less likely to subscribe. It's important to target customers with higher balances.

## Conclusion
The project demonstrates that machine learning models can predict customer behavior with a reasonable level of accuracy. The Random Forest Classifier, after applying data balancing techniques, was the most effective model in this analysis.

## Getting Started
To run this project on your local machine:
1. Clone the repository
2. Install the required dependencies
3. Open the analysis notebook "bank_marketing_analysis"