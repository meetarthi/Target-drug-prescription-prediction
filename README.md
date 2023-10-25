# Target-drug-prescription-prediction

Prescribing Drugs to patients for treating a specific condition or Disease is important for enhancing their health and livelihood. ‘Target Drug’ is a therapy focussed on alleviating the illness, without triggering or altering other bodily functions leading to side-effects. Target drug is administered to the patients in a certain pattern for better results and safety of the patient.

**Objective**
----------------
The objective in this assignment is to develop a predictive model which will predict whether a patient will be eligible for “Target Drug” or not in next 30 days. Knowing  if the patient is eligible or not will help physician treating the patient make informed decision on the which treatments to give.

Data Description 
----------------
The folder shared with you contains following four files
1) Train.parquet - Dataset to be used for training
2) Test.parquet - Dataset to be used for testing

The dataset contains electronic health records belonging to patients who have been diagnosed with a specific disease.The Data has mainly three columns:


1) Patient-Uid - Unique Alphanumeric Identifier for a patient
2) Date - Date when patient encountered the event.
3) Incident - This column describes which event occurred on the day.


Developed using: 
----------------
1. Language - Python
2. Libraries - pandas, scikit-learn, xgboost, hyperopt

Workflow
---------
ML Algorithm - **XG boost**(Implemented Binary classification on the data)

**Training Data Preparation**
1. Import all necessary packages
2. Load data from a Parquet file using Pandas and PyArrow
3. Identify unique values in the 'Incident' column
4. Sort the column 'Patient_Uid' based on the date
5. Create a positive set dataframe with data containing incident - target drug. The data will be in the positive set if the time difference with the previous incident is more than 30 days. This dataframe would contain the Patient-Uid,Incident and target as the columns and the values in the target column is set to 1.
6. Create a negative set dataframe with data where the patient doesn’t have Target drug in incident Or where patient has Target drug in incident, and more than 30 days difference with the previous incident.This dataframe would contain the Patient-Uid, Incident and target as the columns and the values in the target column is set to 0.
7. Create a dataframe ‘train_csv’ by Concatenating the dataframes - Positive and negative set and
Shuffle it randomly for better model training by reducing the bias.

**Feature engineering and model training and testing using training data**
8. Select the feature ‘Incidents’ and assign to variable ‘X’ and convert it to categorical data type.
9. Select the label ‘Target’ and assign to variable ‘y’ and convert it to categorical data type.
10. Split the data into training and testing sets 
11. Initialize XGBoost classifier and specify hyperparameters for tuning. Fit the model to the training data and optimize hyperparameters using GridSearchCV.
12. Make prediction on testing set using the trained model.
13. Calculate model’s accuracy and F1 score.

**Predicting the labels for the test set**
14. Predict the labels for the test set using the model trained.
15. Merge the predicted labels with the test set.
16. Drop the column ‘Incident’ from the test set.
17. Save the test set to csv format.
