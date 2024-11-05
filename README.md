# Time Series Forecasting 2021
 
 Time Series Analysis and Forecasting with SARIMA, SARIMAX, and Prophet
This project involves time series analysis and forecasting, using SARIMA, SARIMAX, and Prophet models on web page view data. This README provides an overview of the project, setup instructions, and details on code usage.

Table of Contents
Project Overview
Dataset
Setup Instructions
Data Preprocessing
Exploratory Data Analysis
Modeling Techniques
SARIMA Model
SARIMAX Model
Prophet Model
Evaluation Metrics
Feature Engineering
Results and Analysis
Further Enhancements
Project Overview
The aim of this project is to forecast page views for various languages and access types. The primary tasks include:

Data cleaning and preparation
Seasonal-Trend decomposition
Time series forecasting using SARIMA, SARIMAX, and Prophet models
Evaluation of model accuracy using metrics such as Mean Absolute Percentage Error (MAPE)
Dataset
The dataset consists of time series data on page views for multiple web pages, with fields for Page, date columns indicating views, Source, Language, and Access Type.

Setup Instructions
To set up and run this project, install the required libraries:

pandas numpy matplotlib seaborn statsmodels scikit-learn prophet

Data Preprocessing
Data Cleaning:

Dropping rows with all NaN values.
Dropping columns with high NaN counts.
Feature Extraction:

Extracting features such as Language and Access Type from the Page column.
Filtering data based on Language with significant representation in the dataset.
Time Series Transformation:

Using pd.melt to unpivot the data, creating date and Reading columns.
Exploratory Data Analysis

Missing Values Analysis: Visualized the missing values per date to assess data quality.

Trend Analysis: Plotted time series data for popular languages.
Seasonal Decomposition: Applied additive and multiplicative decompositions to analyze trend and seasonality.
Modeling Techniques
SARIMA Model
We started with SARIMA, testing various combinations of seasonal and non-seasonal parameters, using ACF and PACF plots to identify p, d, q values.

SARIMAX Model
SARIMAX was implemented to include an external variable Exog (representing marketing campaign data).

Prophet Model
The Prophet model was included to forecast trends and seasonality.

Data Preparation for Prophet: Converted the time series data to Prophet's required format, with ds for dates and y for values.
Model Training and Forecasting: Trained the Prophet model with daily seasonality and a yearly seasonality componen.

Feature Engineering
We engineered features including:

last 7-day avg: Rolling average of last 7 days.
last 14-day avg: Rolling average of last 14 days.
Day of the week: Converted to dummy variables for regression.

Results and Analysis
SARIMA: Showed a general trend and seasonality fit but could be further improved by adding exogenous factors.
SARIMAX: Improved performance by incorporating external campaigns with a MAPE of around 6%.
Prophet: Handled trends and seasonality well, especially with added flexibility for holidays and campaigns.