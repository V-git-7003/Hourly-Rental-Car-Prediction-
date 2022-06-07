"# Hourly-Rental-Car-Prediction-" 
Problem: The main objective of the problem is to
develop the machine learning approach to forecast
the demand of car rentals on an hourly basis..
EDA and Feature Engineering
1. After checking the usual df.info() and df.describe() for any obvious anomalies.
2. The focus was on determining the appropriate features.
3. In this effort a plot of actual/frequency of the demand with respect to the hour and date is
made.
4. The plot between the demand and date made me realize there could be a connection
between:
a. Weekdays
b. Months
c. Years
d. Week of the year
with demand.
5. The connection for some may be more apparent than others like the ‘weekdays’ with
‘demand’.
6. Hence, derived those features front the ‘date’ col.
7. Next agenda was to focus on if ‘demand’ is linearly or non-linearly related to the
features.
8. The box plot and distplot showed clear right-ward skew.
9. During further EDA, it was found that the demand with most frequency is for 93 cars that
occurs mostly on Wed.
10. Making Wednesday as days with most consistent demand albeit the demand being lower
compared to the other days of the week
11. The heatmap of the correlation plot showed no direct linear relationship with the
‘demand’.
12. Some more observations are:
a. The demand frequency is highest on Friday, Saturday and Sunday, respectively,
with least demand on Thur.
b. The actual (not frequency) demand is highest on Saturdays followed by Sunday
and then Friday.
c. At 4:00 pm the demand frequency is highest for cars
d. At 3:00 am the demand frequency is least for cars
e. Frequency of different hours in the data is imbalanced among the early morning
hours of 12:00 am to 6:00 am
f. ‘Demand’ with respect to both week day and time is highest between 12:00 pm to
16:00 pm on Saturday, followed by Sunday and Friday
Model and validation
13. Therefore, we need to use a non-linear model that is immune to imbalanced data. The
base line model I started with is decision tree, followed by random forest with
hypertuning and finally a ANN.
14. The random forest hypertuned on:
a. 'n_estimators',
b. 'Max_features'
c. 'Max_depth'
d. ‘'min_samples_split'
e. 'Min_samples_leaf'
f. 'bootstrap'
15. The RMSE value on the validation data for the various models were
a. Decision tree : 45.1
b. Random forest with out hyperparameter tuning: 34.07
c. Random forest with hyperparameter tuning:32.57
d. ANN with slightly overfitting: 35 (what is displayed in notebook now is corrupted
due to inverse scaling transform)
16. Hence, choose the Random forest model with hyperparameter tuning to perform the
prediction on the test data.
