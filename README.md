# Electricity Price Classification (Austria)

## Overview

In this project, I used machine learning to classify Austrian day-ahead
electricity prices into high and low values. Instead of predicting the
exact price, I simplified the problem into a binary classification task.

## Dataset

The data comes from the Open Power System Data -- Time Series dataset.\ https://data.open-power-system-data.org/time_series/ 
File used: `time_series_60min_singleindex.csv`

Selected features: - load (actual and forecast) - day-ahead price -
solar generation - wind generation

## Approach

I cleaned the data by: - removing rows with missing prices - filling
missing solar and wind values with 0

Then I created additional features: - hour - day of week - month -
weekend (yes/no)

The target variable is based on the median price: - price \> median →
high (1) - price ≤ median → low (0)

## Models

I trained: - Logistic Regression (with scaling) - Random Forest

Data split: - 70% training - 15% validation - 15% test

## Results

Random Forest performed slightly better.

Example: - Validation Accuracy ≈ 0.76 - Validation F1 ≈ 0.79 - Test
Accuracy ≈ 0.53

The model predicts low prices better than high prices.

## Outputs

-   Model comparison plot
-   Confusion matrix
-   Feature importance plot

## How to run

1.  Activate your Python environment and Install dependencies: pip install -r requirements.txt

2.  Place dataset in: ../data/time_series_60min_singleindex.csv

3.  Run the script
