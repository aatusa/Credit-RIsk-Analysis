# Credit_Risk_Analytics
Technologies used: python, pandas, sklearn, seaborn, excel, jupyter.

## Problem Description
The objective of the credit risk analysis is to assess the borrowers' creditworthiness by quantifying the risk of loss to which the lender is exposed. The probability of default, loss due to default, and exposure to default are the three measures that lenders use to measure credit risk.

This is the data set of mortgage observations for 50,000 residential U.S. mortgage borrowers over 60 periods, 600,000 records in total. The data set is a randomized selection of mortgage-loan-level data collected from the portfolios underlying U.S. residential mortgage-backed securities (RMBS) securitization portfolios and provided by International Financial Research (www.internationalfinancialresearch.org).

We have applied SVM, Random Forest, KNN, Logistic Regression Classfication models to determine whether the borrower is able pay their loan(0) or not(1) at the end of the maturity period.

## Data exploration and processing
In this dataset there are two variables - time: Time stamp of observation and orig_time: Time stamp for origination
Based on these columns we have derived a column maturity_time_period_days which is difference between these two varibales. By adding this column we can know in how many days the loan has been paid or how many days are there for the loan to reach the maturity.

The variable orig_time has values of when the obervation of the loan started. So, we added a column name start_day_observation. This new column contains the subtraction of orig_time and first_time. This new column has the number of day on which the loan obeservation started during the Maturity Time Period (maturity_time_period_days).

The dataset has 600,000 records/observation of 50,000 customers. So, in order to obatin a single record for an individual customer we are performing Group By based on id of Customer. So, for this start_day_observation variable we have taken the first value in each group of the customer. The variable start_day_observation contains that day at which the obersvation of Mortagage started from the total maturity_time_period_days.

For the variable balance_time we have different amount varying from 0 to 8,70,1859 dollars. So, in order to efficiently analyze our data we are calculating the percentage difference and standardize the data in a scale. The percentage change is between the beginning balance and ending balance.

We will use SMOTE to upsample our dependent variables. SMOTE is a method of oversampling which produces synthetic samples from the minority class. It is used to achieve a synthetically class-balanced or almost class-balanced training set, which is then used to train the classifier.



## Model building and training
We have build four different models to predict our output variable, that are: 
1. SVM(Support Vector Machines)

2. Random Forest Classifier

3. KNN

4. Logistic Regression.


## Conclusion
After analyzing all the different learning rates and methods we used, the Accuracy that we got was 79% using Random Forest Classifier. The average precision score we received is 0.79.
