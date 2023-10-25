# Target-drug-prescription-prediction

Prescribing Drugs to patients for treating a specific condition or Disease is important for enhancing their health and livelihood. ‘Target Drug’ is a therapy focussed on alleviating the illness, without triggering or altering other bodily functions leading to side-effects. Target drug is administered to the patients in a certain pattern for better results and safety of the patient.

**Objective**
----------------
The objective in this assignment is to develop a predictive model which will predict whether a patient will be eligible for “Target Drug” or not in next 30 days. Knowing  if the patient is eligible or not will help physician treating the patient make informed decision on the which treatments to give.

**Data Description **
----------------
The folder shared with you contains following four files
1) Train.parquet - Dataset to be used for training
2) Test.parquet - Dataset to be used for testing

The dataset contains electronic health records belonging to patients who have been diagnosed with a specific disease.The Data has mainly three columns:


1) Patient-Uid - Unique Alphanumeric Identifier for a patient
2) Date - Date when patient encountered the event.
3) Incident - This column describes which event occurred on the day.


**Developed using: **
----------------
1. Language - Python
2. Libraries - pandas, scikit-learn, xgboost, hyperopt

**Workflow**
---------
ML Algorithm - **XG boost**(Implemented Binary classification on the data)

**Training Data Preparation**
