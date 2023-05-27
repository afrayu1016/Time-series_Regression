# Time-series_Regression

## Env
* Run on Google Colab
* package
```
- numpy
- pandas
- string
- nltk
- re
- sklearn
- gensim
- Word2Vec
```
## Context
This dataset consists the air quality data in Hsinchu area in 2021. Use time series analysis and regresion to predict the PM2.5 value from October to December in 2021.

## Dataset 
* _ 2021.xls
* Dataset columns:
  > 測站: place
  > 日期: detection time
  > 測項: detection item
  > 0~23: hour
## Data preprocessing
* Extract data from October to December
* Split into training data : October and November, testing data: December
* Produce the time series data
  - transfer 18 attibutes into rows
  - columns represent the hour data
  - the vector would be (18 * 61 * 24) (61 days mutiply 24 hours)

## Model 
* Linear Regession
* XGBoost

## Output
* predict 
  - The 1st hour in future
    Take 6 hours as a unit cut. For example, the first data is the data of the 0th to 5th hour to predict the PM2.5 value of the 6th hour. 
  - The 6th hour in future
    Take 6 hours as a unit cut. For example, the first data is the data of the 0th to 5th hour to predict the PM2.5 value of the 11th hour.
* Evaluation: MAE
  Predict by PM2.5 attribute
  - LR MAE(predict 1st hour of PM2.5): 2.680275
  - LR MAE(predict 6th hour of PM2.5): 2.635699
  - xgboost MAE (predict 1st hour of PM2.5):  3.596774193548387
  - xgboost MAE (predict 6th hour of PM2.5):  5.393817204301075
  Predict by 18 attributes
  - LR MAE(predict 1st hour of PM2.5) : 4.276428
  - LR MAE(predict 1st hour of PM2.5):  4.237442
  - xgboost MAE (predict 1st hour of PM2.5):  3.704301075268817
  - xgboost MAE (predict 6th hour of PM2.5):  5.643817204301075
