# Bike Sharing Linear Regression Model
>  This project is part of upGrade IIIT-B ML/AI program curriculum. The objective of this project is to build a multiple linear regression  model for the prediction of demand for shared bikes.


## Table of Contents
- [Bike Sharing Linear Regression Model](#bike-sharing-linear-regression-model)
  - [Table of Contents](#table-of-contents)
  - [Problem Statement](#problem-statement)
  - [Business Goal](#business-goal)
  - [Data Preparation:](#data-preparation)
  - [Model Building](#model-building)
  - [Data Understandig](#data-understandig)
  - [License](#license)
  - [Assignment Steps](#assignment-steps)
    - [1. Data Understanding](#1-data-understanding)
    - [2. Data Cleaning](#2-data-cleaning)
    - [3. Visualizing the Data](#3-visualizing-the-data)
    - [4. Data Mapping and Scaling](#4-data-mapping-and-scaling)
    - [5. Preparing Modelling data](#5-preparing-modelling-data)
    - [6. Model Building and Refinement](#6-model-building-and-refinement)
    - [7. Residual Analysis](#7-residual-analysis)
    - [8. Predict test set value](#8-predict-test-set-value)
  - [Conclusions](#conclusions)
  - [Technologies Used](#technologies-used)
  - [Acknowledgements](#acknowledgements)
  - [Contributors](#contributors)
  - [Contact](#contact)

## Problem Statement
A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 


In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.


They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

- **Which variables are significant in predicting the demand for shared bikes.**
- **How well those variables describe the bike demands**
  

Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors. 

## Business Goal
You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 

## Data Preparation:

1. You can observe in the dataset that some of the variables like 'weathersit' and 'season' have values as 1, 2, 3, 4 which have specific labels associated with them (as can be seen in the data dictionary). These numeric values associated with the labels may indicate that there is some order to them - which is actually not the case (Check the data dictionary and think why). So, it is advisable to convert such feature values into categorical string values before proceeding with model building. Please refer the data dictionary to get a better understanding of all the independent variables.
 
2. You might notice the column 'yr' with two values 0 and 1 indicating the years 2018 and 2019 respectively. At the first instinct, you might think it is a good idea to drop this column as it only has two values so it might not be a value-add to the model. But in reality, since these bike-sharing systems are slowly gaining popularity, the demand for these bikes is increasing every year proving that the column 'yr' might be a good variable for prediction. So think twice before dropping it. 
 

## Model Building

The Model should be built taking the 'cnt' as the target variable. cnt is the sum of casual and registered users who have made a booking on the give day.

## Data Understandig

Data dictionary has been provided in the Readme.txt file and has following details about the dataset.
    
    - instant: record index
    - dteday : date
    - season : season (1:spring, 2:summer, 3:fall, 4:winter)
    - yr : year (0: 2018, 1:2019)
    - mnth : month ( 1 to 12)
    - holiday : weather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
    - weekday : day of the week
    - workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
    + weathersit : 
        - 1: Clear, Few clouds, Partly cloudy, Partly cloudy
        - 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
        - 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
        - 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
    - temp : temperature in Celsius
    - atemp: feeling temperature in Celsius
    - hum: humidity
    - windspeed: wind speed
    - casual: count of casual users
    - registered: count of registered users
    - cnt: count of total rental bikes including both casual and registered

## License

Use of this dataset in publications must be cited to the following publication:

[1] Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, doi:10.1007/s13748-013-0040-3.

@article{
    year={2013},
    issn={2192-6352},
    journal={Progress in Artificial Intelligence},
    doi={10.1007/s13748-013-0040-3},
    title={Event labeling combining ensemble detectors and background knowledge},
    url={http://dx.doi.org/10.1007/s13748-013-0040-3},
    publisher={Springer Berlin Heidelberg},
    keywords={Event labeling; Event detection; Ensemble learning; Background knowledge},
    author={Fanaee-T, Hadi and Gama, Joao},
    pages={1-15}
}

## Assignment Steps 

### 1. Data Understanding
- Import the data from the day.csv file.
- Understand different variables based on the data dictionary.

### 2. Data Cleaning
- Drop Unwanted columns
- Null Value check
- Duplicate Value check

### 3. Visualizing the Data
- Visualize the Numberical Variables to understand patterns and correlations
- Plot Correlation map to identify highly correlated variables with target variable
- Visualize categorical variables

### 4. Data Mapping and Scaling
- Map Categorical Variables
- Create Dummy Variables

### 5. Preparing Modelling data
- Splitting data in train and test sets
- Scaling the variables

### 6. Model Building and Refinement
- Build initial model and use RFE, VIF/p-values to select appropriate variables.
- Refine models in multiple iterations.

### 7. Residual Analysis
- Use last model to predict target value for train set.
- Calculate residuals for train set.
- Validate residual assumptions for linear regression

### 8. Predict test set value
- Use the last model to predict target value for test set.
- Calculate R2 score for test set.

## Conclusions

- The R-squared value of the train set is 79.8% whereas the test set has a value of 79.17% which suggests that our model broadly explains the variance quite accurately on the test set and thus we can conclude that it is a good model.

- RFE was used for the automated selection of variables to start with, VIF and p-values were used to flesh out the most significant variables.

- Significant variables to predict the demand for shared bikes
    - yr
    - holiday
    - temp
    - Season
    - month (jul, sep)
    - weathersit(Clear, Few clouds, Partly cloudy, Partly cloudy)

- Temp, Yr and weathersit 1 is by far the most significant variables in the model.

## Technologies Used
- Python - version 3.11.4
- Matplotlib - version 3.7.1
- Numpy - version 1.24.3
- Pandas - version 1.5.3
- Seaborn - version 0.12.2
- Statsmodels - version 0.14.1
- Scikit-learn - version 1.4.2

## Acknowledgements
Give credit here.
- Upgrad Team and instructors

## Contributors
 - Vijay Kumar

## Contact
Created by [@kumarvijay370](https://github.com/kumarvijay370/) 

Developed as part of the Linear Regression Module required for Post Graduate Diploma in Machine Learning and AI - IIIT, Bangalore by Upgrad.