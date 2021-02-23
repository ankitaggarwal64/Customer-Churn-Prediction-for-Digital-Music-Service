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
- While comparing the evaluation metrics, we clearly see with logistic regression, the F1 score actually improved significantly from 0.09 to 0.42 when we considered the weight of classes to deal with the imbalance present in our data.
- Among the tree-based models, Gradient Boosted trees performed actually performed better than Random forest. However, we have not considered probability thresholds and class weights until now with Gradient Boosted trees and Random forest which can further improve these models' performance. The default threshold of 0.5 is considered right now to calculating F1 scores for Gradient Boosted trees and Random forest.
- Different models are suggesting different importances for different features. Some of the important features we find put accross models are the average number of sessions per day, the fraction of submit downgrade activity, and user age. 
- One of the probable reasons for overall weak F1 performance among models can be because of the size of the data considered. Modeling with a larger dataset can stabilize and can show the actual performance of the models.

![alt text](https://github.com/ankitaggarwal64/Customer-Churn-Prediction-for-Digital-Music-Service-with-PySpark/blob/main/results_summary.PNG)
  
## Acknowledgements <a name="Acknowledgements"></a>
The 'medium-sparkify-event-data.json' dataset has been provided by [Udacity](https://www.udacity.com/) 

