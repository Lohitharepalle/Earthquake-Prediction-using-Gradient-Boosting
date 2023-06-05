# Earthquake Prediction using Gradient Boosting
The aim of this project is to predict the earthquakes using gradient boosting. It provides a graphical user interface (GUI) built with Tkinter, a Python library for creating GUI applications, and utilizes XGBoost, a popular gradient boosting library, for predicting earthquakes.

Earthquake prediction is a challenging task due to the complexity and unpredictability of seismic events. Traditional methods have relied on analyzing historical data and identifying patterns to forecast earthquakes. However, recent advancements in machine learning techniques, particularly gradient boosting, have shown promise in improving the accuracy of earthquake prediction models. Gradient boosting is an ensemble learning algorithm that combines multiple weak predictive models to create a robust and accurate model. In the context of earthquake prediction, gradient boosting algorithms can effectively capture intricate patterns and correlations between various geophysical features, leading to more reliable predictions.

## Problem Statement
To reduce the damage caused by earthquakes, we wanted to develop a machine learning model that can accurately predict earthquake events using GNSS data. This is important because earthquakes can cause significant damage to infrastructure and loss of life, and accurate prediction can help to mitigate their impact and save lives. This model uses Gradient Boosting and is able to identify patterns and trends in the GNSS data that are indicative of impending earthquakes and provide timely alerts to relevant authorities and the public.

## Modules
The project is divided into four different phases
1. Data Collection and Preprocessing
2. Feature Engineering
3. Training the model
4. Evaluation and Prediction

## Implementation
  The data is collected form USGS website (https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_month.csv). Every time the user accesses the application, latest data is downloaded and appends it to the existing data. The data is preprocessed to remove the duplicate tuples added when new data is appended, to handle null values and missing values and to standardise the data to prevent certain features from dominating the model due to their larger magnitudes.

  Feature engineering involves transforming raw data into meaningful features that can improve the performance of a predictive model. It aims to extract relevant information from the available data and create new features that capture important patterns or relationships. In our project, as a part of feature engineering we computed the rolling averages for the depth and magnitude attributes using different window sizes like 22, 15, and 7, shifted the magnitude average for 7 days by a specified number of days to create the outcome column and calculated the mean latitude and longitude values for each unique place in the place column.

  The data is split into training data set and testing dataset and the XGBoost model is successively trained on the dataset and defined parameters.Then the model is tested on the test dataset and its performance is evaluated based on the predictions made by the model on the test dataset.

## Results
   There are three different views of the map in the GUI which includes Google normal view, Satellite view, Open street map view. The GUI consists of a date picker to select the date and an Earthquake estimates button to predict the earthquake occurence on the selected date. If the date selected is not within the range of prediction of the model it shows a warning message, else the predictions are plotted on the map. The experimental results showed that the recall value of the model was 85% indicating that it was able to accurately identify a significant portion of the upcoming earthquake events.
  
