# SC5010_IBM_Data_Analysis

## 1. Environment:
```
pip install numpy  
pip install pandas  
pip install sklearn  
pip install opencv  
pip install seaborn  
pip install os  
pip install matplotlib
pip install imblearn
```  

## 2. Project Objectives:
### 2.1 Dataset Description:
IBM employee data with 35 columns (features) and 1470 rows.
```
https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset
```
Data Set : IBM HR Analytics Employee Attrition & Performance
35 Variables & 1470 Rows
- Personal info: Gender, Age, Education, Marital Status, etc.
- Work Experience: Job Level, Num Companies Worked, etc.
- Company Rating: Job Involvement, Daily\Monthly Rating, etc.
- Working Condition: Distance from Home, Business Travel, etc.
- Benefits: Monthly Income, Percent Salary Hike, etc.

### 2.2 Objective Questions:
#### Q1: What factors matter most in their attrition decision?
#### Q2: How to prevent employees from resigning?

## 3. Project Structure:
```
graph TD;
    A[Step1: Data Preparation]-->B[Step2: Exploratory Data Analysis];
    B-->C[Step3: Machine Learning Algorithm];
```

### 3.1 Step1:
Raw data 
-> Drop Meaningless Features  
-> Category Variable Transformation  
         -> Principal Components Analysis  
         -> Cleaned Data
### 3.2 Step2:


2.
standard, then pca
PCA provides a mapping between the number of principal components and the proportion of variance explained. PCA transforms a set of correlated variables to a new set of uncorrected variables. If the original variables are already near uncorrelated then nothing could be gained by PCA. PCA to reduce the number of features and avoid overtting.


## 4.MACHINE LEARNING APPROACHES

In this project, we focused on constructing robust and reliable ML models for the IBM dataset classication. A total of five ML models were investigated: Logistic Regression (LR), Decision Tree (DT), Random Forest (RF), Support Vector Machines (SVM) and eXtreme Gradient Boosting (XGBoost). The details and performances of the models will be discussed as follows.

For each model, we trained our model in five separate stages. 

a) Firstly, we split our data randomly into 80% train and 20% test, then, we trained and tested each model after performing normalization and PCA to see the approximate accuracy and F1 score of each model. Apart from the accuracy, we also introduced the F1 score here to measure model performance. F1 score is calculated as the harmonic mean between precision and recall, ensuring considerations of incorrect classifications while penalizing extreme values. 

b) Then, we balanced our train dataset by using SMOTE, and trained and tested each model to see whether the accuracy and F1 score of each model had improved after overfitting. 

c) The next step is to try some hyperparameter tuning to tweak our models to try and get better predicting performance. The hyperparameters for each model are listed below. Hyperparameters can be thought of as “settings” for a model. The perfect settings for one dataset won’t be the same for another, so we had to “tune” the model. We started with RandomSearchCV to consider a wide range of values. RandomSearchCV is instantiated, our model was passed in first, followed by our hyperparameters, the number of iterations to try, and the number of cross-validations to perform. We created bar plots of each hyperparameter on the x-axis, and the mean score of the models made at each value, to see which values were most successful on average. We extracted insights about how well each value for each hyperparameter performed on average and took these insights and moved into the second round of hyperparameter tuning to further narrow our selections. 

d) After using RandomSearchCV, we used GridSearchCV to perform a more refined search for our best hyperparameters. The hyperparameters were the same, but now we performed a more exhaustive search using GridSearchCV. In GridSearchCV, every single combination of hyperparameter values was tried which took much more computational power than RandomSearchCV, where we could directly control how many iterations we want to try. 

e) After performing RandomizedSearchCV followed by GridSearchCV, we could call best parameters to get the one best model to try and classify our data. Finally, we created confusion matrices for each model, and computed accuarcy and F1 score, to see how well each model was.


## 5. Results
Summary of the models' performance

|           | Logistic<br>Regression | SVM   | Decision<br>Tree | Random<br>Forest | XGBoost |
| --------- | ---------------------- | ----- | ---------------- | ---------------- | ------- |
| Accuracy  | 0.864                  | 0.847 | 0.765            | 0.864            | 0.830   |
| Precision | 0.548                  | 0.600 | 0.288            | 0.654            | 0.429   |
| F1-score  | 0.535                  | 0.118 | 0.355            | 0.459            | 0.265   |
| Recall    | 0.523                  | 0.065 | 0.463            | 0.354            | 0.191   |
