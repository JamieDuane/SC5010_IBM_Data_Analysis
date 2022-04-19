# SC5010_IBM_Data_Analysis




2.
standard, then pca
PCA provides a mapping between the number of principal components and the proportion of variance explained. PCA transforms a set of correlated variables to a new set of uncorrected variables. If the original variables are already near uncorrelated then nothing could be gained by PCA. PCA to reduce the number of features and avoid overtting.


4.MACHINE LEARNING APPROACHES

In this project, we focused on constructing robust and reliable ML models for the IBM dataset classication. A total of five ML models are investigated: Logistic Regression (LR), Decision Tree (DT), Random Forest(RF) Support Vector Machines (SVM) and eXtreme Gradient Boosting (XGBoost). The details and performances of the model will be discussed as follows.

For each model, we trained our model in three separate stages. We first trained and tested each model after normalization and PCA to see the approximate accuracy and f1 score of each model. Apart from the accuarcy, we also introducted the F1 score to measure model performance. F1 score is calculated as the harmonic mean between precision and recall, ensuring considerations of incorrect classications while penalizing extreme values. Then, we balanced our train dataset by using SMOTE and trained and tested each model to see whether the accuracy and f1 score of each model has improved after balancing. 
