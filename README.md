# US-Adult-Salary-Prediction-ML-App
### LINK TO THE WEBAPP: https://share.streamlit.io/xtric6/us-adult-salary-prediction-ml-app/main/app.py
This repository contains supervised classification models built with python. This models were deployed to a WEB APP using SREAMLIT that can be used to perform EDA on the data and also predict if an adult in the US in the US earns less than or more than $50,000.

## USE CASE
- In the financial sector it can be used to get insights into a persons earning to know if they qualify for a form of loan
- In a business setting can be used to know products to market to a customer based on the customers earning capacity
- Can be applied to other sectors based on the business need.

## Data Understanding
#### The data was gotten from UCI repository and can be accessed with this link: https://archive.ics.uci.edu/ml/machine-learning-databases/adult/

#### The data contains 15 columns and 32561 rows

###### It contains the following attributes:
- ****age**** : continuous.
- ****Workclass**** : Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked.
- ****fnlwgt**** : continuous.
- ****education**** : Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool.
- ****education-num**** : continuous.
- ****marital-status****: Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse.
- ****occupation****: Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces.
- ****relationship**** : Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried.
- ****race**** : White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black.
- ****sex**** : Female, Male.
- ****capital-gain****: continuous.
- ****capital-loss****: continuous.
- ****hours-per-week : continuous.
- ****native-country**** : United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands.

## Data Cleansing
- The data contained duplicates that were dropped.This reduced the number of rows to work with to 32537. This is a reduction of less than 1%.
- The data contained '?'s as one of the unique values in the workclass columns. All question marks were removed all through the entire dataset.

## Exploratory Data Analysis
- Whats the distribution of our target column of adults that earn <=$50 and those that earn >$50
![salary value counts](https://user-images.githubusercontent.com/40510766/149764566-19b8182f-2047-4649-82b3-35c40d1729da.JPG)

The target column Salary had more adults that earn less than <$50,000 compared to adults that earn more tahn $50,000. The adults earning less than $50,000 had 68% more data than the latter.
This knowledge will enable us evaluate our machine learning model with the right metric. Since this is an imbalanced datasset,using accuracy for the evaluation will not give the  actual performace of our ML model. metrics like F1 score,precison,recall and roc-auc-score will be used to evaluate our models.

- How is the 'workclass' distributed/represented in our dataset?
![salary workclass distribution](https://user-images.githubusercontent.com/40510766/149765722-8768ed9a-b543-4af7-acfd-60e6b68431bd.JPG)

We have more data on adults that work in the private sectore in our dataset.

## MODELS USED
- Logistic regression
- Decision tree classifier
- Bagging Classifier
- Random forest

## MODEL Evaluation Techniques USED
- confusion matrix
- roc-auc-score
- accuracy
- cross validation
- classification report

## Model Interpretation Technique Used
- ELI5
- Information gain(Used On random Forest)

## MODEL DEPLOYMENT METHOD USED
- Streamlit

## WEB APP Description/components
- The web app performs the following functions
- **EDA (Exploratory data analysis that can be performed on the dataset on the webapp)**
- On the web app the dataset can be previewed
- The number of rows and columns can be gotten
- its correlation plot can be viewed inside the webapp
- Also its summary statistics(description of data) can be viewed on the web app
![streamliteda](https://user-images.githubusercontent.com/40510766/149770465-e99dd905-ffc5-4bb2-b814-86d59171ad53.JPG)
This shows the heatmap/correlation plot of the features of the dataset
![streamliteda2](https://user-images.githubusercontent.com/40510766/149771108-9e01ded6-5e2b-46e0-a2de-890b88516e26.JPG)

- **PREDICTIONS**
- Any of three models can be used to predict an outcome:
 - Linear Regression
 - Decison tree calssifie and 
 - Bagging Classifier
![salaryprediction1](https://user-images.githubusercontent.com/40510766/149773271-95f563ad-dfce-4337-882d-d09fb0c4fbc7.JPG)
    - Prediction made with Logistic Regression Classifier
![salary prediction2](https://user-images.githubusercontent.com/40510766/149773362-75e39a69-b720-463b-8e65-158614943f36.JPG)
    - Prediction made with Decision Tree
![salary prediction3](https://user-images.githubusercontent.com/40510766/149773374-00532410-44bd-472b-a21b-6f106358e4f7.JPG)
    - Prediction made with Bagging Classifier
![salary prediction4](https://user-images.githubusercontent.com/40510766/149773385-64622697-5af3-4845-a1ed-4b423585e00c.JPG)
 
- **METRICS**
 - This part of the web app is where predictions are stored in a database(data.db). it can be accessed using sqlite
![salary prediction5](https://user-images.githubusercontent.com/40510766/149773393-2a9b909b-5b2b-40bd-ab16-82ca728b407f.JPG)
 - Acessing the information in the database(data.db) and table (predictiontable)
  - in the database created a the table created was named predictiontable.All codes showing this are in app.py
   ![salary db](https://user-images.githubusercontent.com/40510766/149777677-16fa2ade-0802-48dc-8a2a-fc1f3a34ced1.JPG)
   
## CONCLUSION
- RandomForest had the best accuracy and roc-score but in terms of correctly predicting our minority label (>50$ ) or 1 as its represented after encoding it performed poorly.
- Decisiontree classifier was the best model among all models trained. it was able to predict our minority label better than other classifiers. This was evalauted using the confusion matrix. Bagging classifier(Bc) had the least False negative(FN)  value which made it better than other classifier in predicting the minority class.
- Although the bagging calssifier predicts quite precisely. Its more slower than other classifiers in making predictions.

## WAYS PROJECT COULD BE IMPROVED
- Adding a time column to the predictiontable that shows when each user makes a prediction
- Stripping off all white spaces from the data.
- Collecting data of correct predictions from users incase an incorrect prediction is made. This can help us better evalaute our models performance on unseen data.






