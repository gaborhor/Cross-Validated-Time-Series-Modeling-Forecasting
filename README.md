# Cross-Validated Time Series Modeling & Forecasting

## Overview:
This personal project aims to apply XGBoost in modeling and forecasting Time Series energy consumption data from PJM Interconnect's Eastern seaboard.

## File Glossary:

gh_timeseries_project.ipynb :
  
  Jupyter Notebook with python code implementing Pandas, Scikit-Learn, and XGBoost in exploring Time-Series hourly energy consumption (mW) data.

PJME_hourly.csv :
  
  Time-Series hourly energy consumption (mW) data from PJM Interconnection LLC, specifically from the East region of its USA-based Regional Transmission Network.

/PJME_analysis_predictions/ :
  
  Output directory for all assets produced by 'gh_timeseries_project.ipynb', directly uploaded for convenience. The python code lightly handles redundant file generation should you choose to run the repo contents locally.

## Data Glossary:

Target Feature:
  * ['PJME_MW'] - Energy consumption in 'mW' - TARGET FEATURE FOR MODELING

Time Features:
  * ['hour'] - Label features of Time Series data
  * ['dayofweek'] - Label features of Time Series data
  * ['dayofmonth'] - Label features of Time Series data
  * ['dayofyear'] - Label features of Time Series data
  * ['month'] - Label features of Time Series data
  * ['quarter'] - Label features of Time Series data
  * ['year'] - Label features of Time Series data

__Engineered Lag Features:__
  * ['lag1'] - Engineered feature relating a given 'mW' data point to the same Date and Time 1 year ago
  * ['lag2'] - Engineered feature relating a given 'mW' data point to the same Date and Time 2 years ago
  * ['lag3'] - Engineered feature relating a given 'mW' data point to the same Date and Time 3 years ago

## Tools and Approaches:

* Pandas, Numpy - data handling
* Matplotlib, Seaborn - data visualization and assessment of basic data behavior
* SciKitLearn - error metrics, TimeSeriesSplit, cross-validation
* XGBoost - modeling and forecasting w/ XGBRegressor
* 'os', 'shutil' - local device model and visualization storage

## __Results:__
I was able to model hourly energy consumption from 2002-2018 with Root Mean Squared Error (RMSE) of 3457 mW for predictions on a scale of 20000 to 60000 mW.
Additionally, I was able to forecast a full year's worth of hourly data from 2018-08 to 2019-08, and save the model for future use or adjustment.
