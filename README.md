# Apache Spark for Scalable Machine Learning on BigData

# Predicting Wind Speed and Direction at JFK Airport with Apache Spark

## Introduction

Wind conditions have a direct effect on airport operations, from runway selection to takeoff and landing safety and flight scheduling. Accurate short-term wind predictions help airports plan more efficiently and reduce delays.

This project uses **Apache Spark (PySpark) and Spark MLlib** to build and compare machine learning models on hourly weather observations from **John F. Kennedy International Airport (New York)**, taken from the NOAA weather dataset. It tackles two problems:

1. **Regression:** predicting wind speed (`HOURLYWindSpeed`) from wind direction, elevation and station pressure.
2. **Classification:** predicting whether the wind direction falls in the first or second half of the compass (below or above 180°), using wind speed, temperature, pressure, pressure tendency, precipitation and elevation.

## Approach

- **Data preparation:** loaded the CSV into a Spark DataFrame, cleaned stray characters, cast columns to numeric types, and removed rows with missing or zero wind values.
- **Exploration:** examined feature relationships with a Pearson correlation matrix (for example, wind speed vs. pressure tendency).
- **Feature engineering:** combined features with `VectorAssembler`, scaled them with `Normalizer`, and bucketized wind direction with `Bucketizer`.
- **Modelling:** built Spark ML `Pipeline`s with an 80/20 train/test split.
  - *Regression:* Linear Regression and Gradient-Boosted Trees, evaluated with RMSE.
  - *Classification:* Logistic Regression, Random Forest and Gradient-Boosted Trees, evaluated with accuracy.

## Key Results

- **Best regression model:** *[model name]*, with RMSE of *[value]*.
- **Best classification model:** *[model name]*, with accuracy of *[value]*.
- *[One sentence on the main takeaway.]*

## Tools

Python · PySpark · Spark MLlib · Jupyter Notebook · NOAA JFK weather data
