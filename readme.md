An end-to-end data-intensive application that tracks the inventory of bikes and available docks at a given station 'Broadway & E 14 St' with the Citibike Bike Sharing system in NYC.

1. Extract Transform Load (ETL):\
Followed the medallion format of data development to refine the raw bike and weather information into what the model and application will require at the bronze, silver, and gold level of data quality/refinement.\
Documented the delta tables required at the bronze, silver, and gold levels.\
Processed the historical trip and weather data with an ETL pipeline using a spark streaming job to ingest new data as it comes into the sources.\
Used Partitioning and Z-ordering to optimize delta tables for the application.

2. Exploratory Data Analysis (EDA):\
Used the raw weather and bike trip data to answer the following questions
   1. What are the monthly trip trends for your assigned station?
   2. What are the daily trip trends for your given station?
   3. How does a holiday affect the daily (non-holiday) system use trend?
   4. How does weather affect the daily/hourly trend of system use?

3. Modeling and ML Ops:\
Considering historical data, built a forecasting model that infers net bike change at the assigned station by the hour.\
Used prophet model for forecasting the number of docks at the station, total bikes available, and the available bikes for the next 4 hours.\
Registered the model at the staging and production level within the Databricks model registry.\
Stored artifacts in each MLflow experiment run to be used by the application to retrieve the staging and production models.\
Tuned the model hyperparameters using the MLflow experiments and hyperparameter scaling (spark trials, hyper-opts).

5. Application:\
Created a gold table to store inference and monitoring data.\
Monitored the performance of staging and production models using residual plots that illustrated the error in forecasts.
