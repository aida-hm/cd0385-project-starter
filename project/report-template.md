# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Aida Hashemlou

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?

I could not submit the negative values since they were not accepted by Kaggle
I needed to identify them and set them to zero.

### What was the top ranked model that performed?
Best model: "WeightedEnsemble_L3"

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
- temp & atemp have almost central distribution
- windspeed, count, registered, casual are right skewed
- humidity is almost left skewed
- season & weather are categorical
- holiday and workingday are binary

based on the notebook suggestion I added the hour feature by extracting it from datetime.

### How much better did your model preform after adding additional features and why do you think that is?
the rmse score decreased from 1.80462 to 0.61799 which shows a great improvement
the added 'hour' feature enhanced the score by providing insights into the typical daily demand in bike-sharing, independent of specific dates or times.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
from the initial rmse score of 1.80462 it decreased to 1.4379 which shows some improvement. but it also shows as increase from rmse score 0.61799 gained after adding the extra feature, which means that tuning the hyperparameters further could result in better scores

### If you were given more time with this dataset, where do you think you would spend more time?
tuning hyperparameters to decrease the rmse score

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|-53.134376|-53.134376|-53.134376|1.80462|
|add_features|-30.389407	|-30.389407	|-30.389407	|0.61799|
|hpo|-53.134376 |-30.389407 |-143.480277 |1.4379|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![image](https://github.com/aida-hm/cd0385-project-starter/assets/56322150/02f0da35-a684-47fc-b9f2-11e49d473acc)


### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.
![image](https://github.com/aida-hm/cd0385-project-starter/assets/56322150/9c7efefc-d3c0-4f83-8592-6e2ed57bd8a0)



## Summary
This project explored experimenting with real-world data, highlighting the significance of feature engineering and the optimization of hyperparameters. By utilizing Autogluon, a variety of models were assessed and the the most efficient one was selected. This was an iterative process including addition of features, exploratory data analysis (EDA), and fine-tuning of hyperparameters, aiming to achieve a satisfactory RMSE score.
