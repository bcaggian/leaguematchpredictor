League of Legends Match Predictor
Author: Ben Caggiano
Institution: University of North Carolina at Charlotte

Overview
This is a machine learning project to predict whether the Blue team or Red team will win a League of Legends match based only on the first 10 minutes of gameplay data.
Dataset
The data is from the "League of Legends Diamond Ranked Games (10 min)" dataset on Kaggle. It contains roughly 10,000 matches and tracks 40 different early-game stats like gold, experience, and kills.
What I Did
Data Prep: The dataset was already clean, so no missing value imputation was needed.
Feature Engineering: To make the data a bit more realistic to how players think, I calculated and added two new features:
KDA: (Kills + Assists) / (Deaths + 1)
Objective Control: Total sum of dragons, heralds, and destroyed towers.
Models: I split the data 80/20 and ran two algorithms:
Logistic Regression (to act as a linear baseline).
Random Forest Classifier (to handle complex interactions).
Hyperparameter Tuning: I used GridSearchCV on the Random Forest to test different combinations of tree depths and estimators to find the best possible settings and maximize accuracy.

Results
Logistic Regression Accuracy: ~72.8%
Tuned Random Forest Accuracy: ~73.1%

Conclusion: The models successfully predict the game outcome about 73% of the time just from the first 10 minutes. A feature importance check showed that early game gold and experience differences are the biggest factors. Because these scale pretty linearly with winning, the basic Logistic Regression model performed almost as well as the tuned Random Forest.
