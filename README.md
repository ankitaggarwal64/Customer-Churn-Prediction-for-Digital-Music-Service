# Churn Prediction for Music Streaming Service(with PySpark)


### Table of Contents

1. [Project Overview](#Overview)
2. [Problem Statement](#Statement)
3. [Files Description](#files)
4. [Dependencies](#Dependencies)
5. [Results Summary](#Summary)
6. [Acknowledgements](#Acknowledgements)


## Project Overview<a name="Overview"></a>
In the project, we build a model which can predict in advance the customers who are likely to cancel the Sparkify music streaming service based on available user's past activity and interaction logs data. The project is carried out with PySpark which is a python API for using Apache Spark distributed computing capabilities. 

The complete details and approach of the project can be found [here in this blog post on Medium.](https://ankitaggarwal64.medium.com/churn-prediction-for-music-streaming-service-with-pyspark-761259cc33e8)

## Problem Statement<a name="Statement"></a>
The goal of the project is to build a binary classifier that can accurately predict the users at risk to cancel the service at least one week in advance of their cancellation timeline. This one-week advance window is selected so that company has enough time to reengage with users at risk to churn with incentives and prevent the customer from canceling the service.

![alt text](https://github.com/ankitaggarwal64/Customer-Churn-Prediction-for-Digital-Music-Service-with-PySpark/blob/main/history_and_prediction_horizon.PNG)
  
## Files Description <a name="files"></a>

The files structure is arranged as below:

	- README.md: read me file
	- Sparkify_Project.ipynb: complete project and code details
	- ML Pipeline Preparation.ipynb: contains ML pipeline preparation code
	- history_and_prediction_horizon.png: image for explaining event history and prediction horizon
	- results_summary : snapshot of best model results summary


## Dependencies <a name="Dependencies"></a>
- PySpark Sql and PySpark ML
- Numpy, Pandas
- Matplotlib, Seaborn

## Results Summary<a name="Summary"></a>
- Based on the modeling in this project, we searched for the models with the best parameters with the help of grid search cross-validation and further trained these models on train data and predicted the customer churn labels for test data. 
- While comparing the evaluation metrics, we can clearly see that f1 score of the logistic regression and random forest improved significantly when we considered the weight of classes to deal with the imbalance present in our data. 
- Among the tree-based models, Random forest with considering class weights performed better than gradient boostin based on the parameters we have considered until now. Another area for improvement we have not considered until now is tuning with probability threshold. The default threshold of 0.5 is considered right now to calculating F1 scores for all considered models. 
- Different models are suggesting different importances for different features. Looking at feature importance plots, some of the important features are the average number of sessions per day, the fraction of submit downgrade activity, and user age.
- Among all the models builds on this small dataset, we see that logistic regression when considered with class weights ranked first in terms of f1 performance. This might be because of the parametric nature of the logistic regression which requires less data for training as compared to non-parametric tree based models. This performance ranking of models can change when we train with bigger size of dataset.
- One of the probable reasons for overall weak F1 performance among models can be because of the size of data considered. Modeling with a larger dataset can stabilize and can show the actual performance of the models.

![alt text](https://github.com/ankitaggarwal64/Customer-Churn-Prediction-for-Digital-Music-Service-with-PySpark/blob/main/results_summary.PNG)
  
## Acknowledgements <a name="Acknowledgements"></a>
The 'medium-sparkify-event-data.json' dataset has been provided by [Udacity](https://www.udacity.com/) 

