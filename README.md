# Titanic-Survival
Predicting survival of  passengers on the Titanic, from the Kaggle competition dataset.

After doing some preprocessing and feature engineering, a random forest classifier model was used. The initial submission utilized a simple model with minimal feature engineering and fixed hyperparameters.

Subsequent submissions incorporated hyperparameter tuning. The final submission scored in the top 6% of all competition teams. Below is a quick summary of my submissions.

Prior to submitting my own models, I completed the Kaggle tutorial for this competition and submitted a simple Random Forest Classifier model.

The first RandomForestClassifier model that I created myself had the following key differences from other submissions: 'Age' was split into 4 categories; dummy variables were used for 'Sex' and "Embarked'; model hyperparameters were arbitrarily selected or set to default values. Final score was unchanged from the tutorial submission.

I then ran a logistic regression model with identical features and training data, and received a slightly worse score.

For subsequent submissions, instead of creating dummy variables for 'Sex' and 'Embarked' I simply mapped these categories to numerical values. Furthermore, I split 'Age' into 5 categories instead of 4. These changes slightly improved my score.

I then implemented a nested loop for hyperparameter tuning. The two hyperparameters I tuned were 'min_samples_split' and 'min_samples_leaf'. Furthermore, I manually tried different values for 'n_estimators'. Initially, I had incorporated this hyperparameter into my tuning as well, however this caused the program to run for too long. With the incorporation of this tuning, I was able to acheive my highest submission scores.

In later versions of my model, I used a GridSearchCV method for hyperparameter tuning instead of a nested loop, however this did not improve my score. I also utilized grid search with an XGBClassifier inseat of a RandomForestClassifier, but again, this did not improve my score. Apparently, minimizing the oob_score in the nested loop produces more accurate hyperparameters then the predefined accuracy measures in GridSearchCV. This makes sense, as oob_score is generally a more pessimistic estimator of accuracy.
