# Kaggle Playground Competition: Predicting CO2 Emissions using Sentinel-5P Satellite Observations

Welcome to the 2023 edition of Kaggle's Playground Series! This competition focuses on the important task of predicting future carbon emissions using machine learning models based on open-source CO2 emissions data from Sentinel-5P satellite observations.

## Competition Overview

This competition aligns with the ongoing partnership between Kaggle and Zindi, aiming to drive community-driven impact across Africa. Zindi is a professional network for data scientists to learn, grow their careers, and contribute to impactful projects. The objective of this challenge is to leverage satellite observations to create machine learning models that predict carbon emissions, particularly in regions where on-the-ground monitoring is not feasible.

For more details about the competition, you can visit the competition link:https://www.kaggle.com/competitions/playground-series-s3e20/overview
Since i could not upload the dataset of the competition because it was too big for Github, i'll link where you can download it: https://www.kaggle.com/competitions/playground-series-s3e20/data

# Code Overview

The provided code showcases a comprehensive pipeline for the competition task. Here's an overview of the key sections:

## Data Exploration and Visualization

The code starts by reading the training data from a CSV file and converting the 'date' column to a datetime format.
It performs initial data exploration by displaying the head, summary statistics, and information about the data.
The code checks for missing values in the dataset and prints the count of missing values for each column.
It generates boxplots and grouped boxplots to visualize the distribution of 'num_sold' (number of units sold) across different categories like country, store, and product.

## Time Series Analysis

The code utilizes statistical tools and libraries like statsmodels and seaborn for time series analysis.
It calculates summary statistics for 'num_sold' grouped by different categories (product, store, country).
The code uses pivot_table to reshape the data, generating a time series of the total number of units sold.
A time series plot is created to visualize the overall trend of total units sold over time.

## Feature Engineering

The code creates new variables for day of the year and year from the 'date' column.
Leap days are accounted for, and COVID-related adjustments are made to certain days in 2020.
Features related to even/odd years and weekdays are extracted from the 'date' column.

## Machine Learning Modeling

The code employs a RandomForestRegressor model from scikit-learn to predict the 'num_sold' values.
Features like day of week, month, year, adjusted day of year, and year type are used as input features.
The dataset is split into training and validation sets for model training and evaluation.
The model is initialized, trained, and evaluated using root mean squared error (RMSE) on the validation set.

## Making Predictions and Submission

The code reads the test dataset, performs similar feature engineering steps, and creates input features for prediction.
The trained RandomForest model is used to predict 'num_sold' values for the test set.
The predicted values are plotted against the test dates to visualize the forecasted results.

## Submission

The code reads the sample submission file, replaces the 'num_sold' column with predicted values, and saves the updated submission file.
