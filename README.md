This project implements standalone supervised machine learning models against ensemble models in detecting anomalies and intrusions in Internet of Things (IoT) network traffic. 

Dataset Description

Source: I sourced this dataset from a Public domain, curated by researchers from Ontario Tech University Canada. 

Size: 625,783 rows and 86 columns of which ghe data contains a greater number of attack traffic than normal.

Key features: Includes protocol type, packet size, label information indicating normal vs anomaly activities. 

Exploratory Data Analysis

The dataset underwent some visualization which includes;

1. A pie chart showing protocol usage distribution
   
2. Bar chart showing the attack categories and label
   
3. Pie chart showing category distribution

Data Preprocessing 

- I dropped irrelevant features like (timestamp)

- Categorical features were label-encoded

- Lamda was used to handle floating numbers

- Applied SMOTE and SMOTENC to handle class imbalance issues. but SMOTENC deals with numerical and categorical features (in the case of this project my target variable is the only categorical columns and i already applied label encoder making SMOTE the best to handle imablance issue in the project)

Models Implemented 

1. Logistic Regression

2. Naives Bayes

3. Voting Classifier with various cases of combination of base classifiers;

The first set of base models include;

- Logistic Regression

- Naive Bayes

- Random forest

The second set includes;

- Logistic Regression

- Naive Bayes

- Decision tree

The third set includes;

- Logistic Regression

- Naive Bayes

- Decision tree

- Adaboost

I also explored training Adaboost as a standalone which showed that ensemble models still performs better on a larger dataset. 

Model Comparison

The bar chart above presents a comparative analysis of five different models based on three key performance metrics: precision, recall and f1-score. 

Logistic Regression 

precision: 64%

recall: 87%

f1 score: 68%

While logistic regression performs moderately well, its scores indicate limited capability in accurately identifying anomalies compared to ensemble models. 

Naive Bayes 

Precision:55%

recall: 70.5%

f1-score: 38.5%

This model shows a high rate of false positives and poor overall balance between precision and f1 score, making it less reliable for detecting intrusions

Voting Classifier 1 (Logistic Regression + Naive Bayes + Random Forest) 

precision: 77.5%

recall: 96.5%

f1-score: 84%

The introduction of ensemble learning signifcantly enhances detection performance, especially in percision. 

Voting Classifier 2 (Logistic Regression + Naives Bayes + Decision Tree)

Precision: 77.50%

recall: 96.50%

f1-score: 84%

same metrics as Voting classifier 1, suggesting similar predictive behaviour and generalization 

Voting Classifier 3 ( Logistic Regression + Naive Bayes + Decision Tree + Adaboost) 

Precision: 97%

recall: 98.50%

f1 score: 97.50%

this model outperforms all other, achieving near-perfect scores across all metrics. The addition of adaboost improves the classifiers ability to detect both majority and minority class instances effectively. 

