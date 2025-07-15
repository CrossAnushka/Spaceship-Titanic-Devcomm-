# Spaceship Titanic ML Model

This project predicts whether a passenger was transported to another dimension during the mysterious Spaceship Titanic incident using machine learning.

It was built as part of the Kaggle “Spaceship Titanic” competition and uses XGBoost, a powerful ML model for structured/tabular data.



## Files Used
	•	train.csv – Contains passenger data + the target column Transported
	•	test.csv – Passenger data for which we need to predict Transported
	•	sample_submission.csv – Format required for final submission to Kaggle



## What the Model Does
	1.	Cleans the data
	2.	Extracts features from the Cabin, PassengerId, and spending columns
	3.	Fills missing values
	4.	Label-encodes categorical features
	5.	Trains an XGBoost Classifier
	6.	Evaluates model using validation accuracy
	7.	Outputs a submission.csv file ready to upload to Kaggle
