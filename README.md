# Spaceship Titanic ML Model

This project predicts whether a passenger was transported to another dimension during the mysterious Spaceship Titanic incident using machine learning.



## Files Used
	•	train.csv – Contains passenger data + the target column Transported
	•	test.csv – Passenger data for which we need to predict Transported
	•	sample_submission.csv – Format required for final submission to Kaggle



## What the Model Does
	1.	Cleans the data
	2.	Extracts features from the Cabin, PassengerId, and spending columns
	3.	Fills missing values
	4.	Label-encodes categorical features
	5.	Model training and evaluation (XGBoost & LightGBM)
 	6.	Final predictions on the test set


## ML MODELS USED:
### 1. XGBoost Classifier
- Initial model with decent performance  
- Validation Accuracy: **82.87%**

### 2. LightGBM Classifier 
- Final chosen model for test prediction
- Validation Accuracy: **84.02%**
- Trains faster and handles categorical features efficiently

> **We used LightGBM for the final submission because it outperformed XGBoost in both accuracy and speed.**



## Feature Engineering 
To improve model performance and help it understand hidden patterns in the passenger data, several new features were created from existing columns.
1. **Cabin Breakdown**: Deck, Cabin Number, Side
	•	The Cabin column (e.g., "F/1234/S") was split into:
	•	Deck: Indicates the floor or level of the ship
	•	Cabin_num: Numeric part of the cabin ID 
	•	Side: 'P' (Port) or 'S' (Starboard)

This helped the model learn location-based patterns (e.g., certain decks or sides being more prone to transportation).

2. **IsTopDeck**
	•	A binary feature that is 1 if the passenger is on Deck A or B, else 0.
	•	These decks are assumed to be higher or more luxurious, possibly affecting survival or transportation chances.

3. **IsBackCabin**
	•	A binary feature that is 1 if Cabin_num > 1500, else 0.
	•	Higher cabin numbers may represent cabins located deeper or further back in the ship, which might correlate with greater risk.

 4. **DeckFrequency**
	•	A new numeric feature that shows how many passengers were assigned to each deck.
	•	Decks with more passengers might have had shared fates or behaviors, such as bulk CryoSleep or similar spending habits.

5. **Cabin_num Conversion**
	•	Cabin_num was converted to a numeric column to allow the model to treat it as a meaningful continuous feature.
	•	Missing or invalid cabin numbers were replaced with -1 as a placeholder.

