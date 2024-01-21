# Machine Learning Project to predict Stack Overflow question Score

## Description
This project is a machine learning project that uses the StackOverflow data dump to predict the number of points a question will receive. 

## Dependencies
- Python version >= 3.9
- Jupyter Notebook


## Data
Source: https://www.kaggle.com/datasets/stackoverflow/stacksample


## How its works

### Data preparation
The data preparation process includes loading question and answer data from CSV files, calculating total answer scores, merging this information with the original questions, normalizing text in titles and bodies, and filtering and saving the processed data to a new CSV file.

### Data analysis
This process involves loading processed question data from a CSV file and conducting various analyses. It calculates lengths, word counts, text characteristics, and TF-IDF values on the processed question data. The script also generates a correlation matrix heatmap and saves the analyzed data to a new CSV file.

### Data standardization
The script standardizes analyzed question data by removing outliers and winsorizing extreme values for specific columns. It then saves the standardized data to a new CSV file.

### Model training
The code first loads standardized question data from a CSV file, then transforms it using TF-IDF vectorization, and splits it into training, validation, and test sets. Following that, it trains a Random Forest Regressor model with hyperparameter tuning using GridSearchCV and evaluates the model's performance on the test set in terms of Mean Squared Error (MSE), R^2 score, Mean Absolute Percentage Error (MAPE), and accuracy within a specified tolerance.


## Results
The hyperparameter tuning using GridSearchCV resulted in the best Random Forest Regressor model with the following parameters:

- **max_depth**: 10
- **min_samples_leaf**: 1
- **min_samples_split**: 10
- **n_estimators**: 50

The model's performance on the training set is reflected in the following metrics:

- **Train MSE**: 5.27
- **Train R^2**: 0.46

On the test set, the model performed as follows:

- **Test MSE**: 5.22
- **Test R^2**: 0.45

Additionally, the Mean Absolute Percentage Error (MAPE) for the test set is reported, and the accuracy within ±3 is measured at **87.48%**.


## Conclusion
The Random Forest Regressor model with hyperparameter tuning using GridSearchCV performed well on the test set, with an R^2 score of 0.45 and an accuracy within ±3 of 87.48%. The model's performance could be improved by using a larger dataset, including more features, and using more sophisticated models.

It can be use to predict the number of points a question will receive on Stack Overflow before it is posted. This could be used to help users improve their questions and increase their chances of receiving a high score.



