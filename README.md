# Air-Quality-Index

## Introduction
The air quality index (AQI) is an index for reporting the air quality on a daily basis. It is used by government agencies to communicate to the public how polluted the air currently is or how polluted it is forecast to become. It is a measure of how air pollution affects one's health within a short time period. The purpose of the AQI is to help people know how the local air quality impacts their health and people can plan their day to day activities.

In this project I predict the air quality index by using data from 2013

## Data Collection
I collected data from multiple sources give below

### Data
1. [Weather data for Bangalore](https://en.tutiempo.net/climate/ws-432950.html) - This website consists of html pages. In html_data notebook I retrieved html weather data from 2013 to 2018. I created html files for every month of the year from 2013 to 2018]. The next this is to extract the information from these html files 
2. [AQI Data](https://openweathermap.org/) - I got the AQI data from [Krish Naik](https://github.com/krishnaik06/AQI-Project/tree/master/Data/AQI) because the website contains a paid API. The link contains csv files with data from 2013 to 2018

## Data Preprocessing
- In Html_data.ipynb I have written code to dynamically download html pages by using 'url'
- In **AQI_Plot.ipynb** I took the average of **PM2.5** feature and stored it in a list. I also plotted the data of every year
- I have imported all the functions from **AQI_Plot** into Combine_data.ipynb. I scraped every html file created in **Html_data.ipynb** using **BeautifulSoup**. At the end of the notebook I removed features that had null values or was not needed. I combined the data taken from both sources and created a csv file in **excel** dialect. I read the csv file using pandas and stored it in a datframe so I can continue
- The dependent feature is **PM2.5** and all other features are independent features


## Feature Engineering
- Checked for null values by using pandas and seaborn
- Pairplot to for multivaraite analysis
- Correletaion matrix with heatmap

### Feature Importance 
Since there are many independent features we can get the importance of each feature and the higher the score the more important the feature is. The feature importance is an inbuilt class that comes with **Tree Bases Regressor**. I used **Extra Tree Regressor** for extracting the top ten features

## Machine Learning Models Used 
1. Linear Regression
2. Ridge/Lasso Regression: Used **GridSearchCV** to find best alpha value
3. Logistic Regression
4. Decision Tree Regressor
5. KNN Regressor
6. Random Forest Regressor
7. Xgboost Regressor
8. Hyperparameter Tuning
9. Artificial Neural Network - ANN

I have created pkl files for all the machine learning models that I have used

### Regression Evaluvation Metrics: 
- Mean Absolute Error(MAE)
- Mean Squared Error(MSE)
- Root Mean Squared Error(RMSE)

## Deployment using Flask and Heroku
- The *static* subfolder contains the CSS file and the *template* subfolder contains two html files
- Home.html is the homepage which will have headings and a predict button
- Result.html will help display the result after the prediction
- Pkl file is loaded into App.py and I will call the Flask app 
- A Procfile is a mechanism for declaring what commands are run by your application's containers

## Running the Flask App
- Go to CMD(Command Prompt) and switch to the project folder directory
- Type python app.py and you will recieve the url
- Copy paste the local url and paste it into your browser
- Click on predict button

