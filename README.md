# TITLE
## US-Adult-Salary-Prediction-ML-App
This repository contains supervised classification models built with python. This models were deployed to a WEB APP using SREAMLIT that can be used to perform EDA on the data and also predict if an adult in the US in the US earns less than or more than $50,000.

# USE CASE
- In the financial sector it can be used to get insights into a persons earning to know if they qualify for a form of loan
- In a business setting can be used to know products to market to a customer based on the customers earning capacity
- Can be applied to other sectors based on the business need.

# Data Understanding
* The data was gotten from UCI repository and can be accessed with this link: https://archive.ics.uci.edu/ml/machine-learning-databases/adult/
and contains ****15 columns**** and ****32561 rows****
* It contains the following attributes: age: continuous.
****Workclass**** : Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked.
****fnlwgt**** : continuous.
*****education**** : Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool.
**** education-num**** : continuous.
**** marital-status****: Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse.
****occupation****: Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces.
****relationship**** : Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried.
****race**** : White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black.
****sex**** : Female, Male.
****capital-gain****: continuous.
****capital-loss****: continuous.
****hours-per-week**** : continuous.
****native-country**** : United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands.

# Data Cleansing
- The data contained duplicates that were dropped.This reduced the number of rows to work with to 32537. This is a reduction of less than 1%.
- The data contained '?'s as one of the unique values in the workclass columns. All question marks were removed all through the entire dataset.

# Exploratory Data Analysis
- Whats the distribution of our target column of adults that earn <=$50 and those that earn >$50
![salary value counts](https://user-images.githubusercontent.com/40510766/149764566-19b8182f-2047-4649-82b3-35c40d1729da.JPG)

The target column Salary had more adults that earn less than <$50,000 compared to adults that earn more tahn $50,000. The adults eraning less than $50,000 had 68% more data than the latter.
This knowledge will enable us evaluate our machine learning model with the right metric. Since this is an imbalanced datasset,using accuracy for the evaluation will not give the  actual performace of our ML model. metrics like F1 score,precison,recall and roc-auc-score will be used to evaluate our models.

- How is the 'workclass' distributed/represented in our dataset?
![salary workclass distribution](https://user-images.githubusercontent.com/40510766/149765722-8768ed9a-b543-4af7-acfd-60e6b68431bd.JPG)

We have more data on adults that work in the private sectore in our dataset.

# MODELS USED
- Logistic regression
- Decision tree classifier
- Bagging Classifier
- Random forest

# MODEL Evaluation Techniques USED
- confusion matrix
- roc-auc-score
- accuracy
- cross validation
- classification report

# Model Interpretation Technique Used
- ELI5
- Information gain(Used On random Forest)

# MODEL DEPLOYMENT METHOD USED
- Streamlit

# WEB APP Description/components
- The web app performs the following functions
- *** Exploratory data analysis that can be performed on the dataset on the webapp ***
---- On the web app the dataset can be previewed
---- The number of rows and columns can be gotten
---- its correlation plot can be viewd
---- And its summary statistics(description of data) can be viewed on the web app







