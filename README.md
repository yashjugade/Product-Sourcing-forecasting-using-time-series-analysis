The project is about forecasting the courcing cost of items sourced in June 2021 based on data from July 2020 to May 2021 using Time series analysis.

About the Project
The coding challenge consists of data of sourcing items from July 2020 to May 2021. The challenge is to forecast the sourcing cost of the same items. Two dataset files are provided. The first file consists of training data i.e. data from July 2020 to May 2021 and the second file is of testing data i.e. the actual values of sourcing from June 2021.

The first six columns i.e. ProductType, Manufacturer, Area Code, Sourcing Channel, Product Size and Product Type are all categorical variables and their unique combination makes up a unique item to be sourced. After analysing the dataset a total of 96 unique combinations were found i.e. 96 unique items are usually sourced. There are limited number of feature combinations (including sourcing month). Elaborating the previous statement, the combination of features for many values of sourcing cost (target variable) will be the same, which is a challenge for traditional Machine Learning Regressors. Thus, I have chosen to explore and apply the Time series based machine Learning technique.

I have tried to analyse the periodic trends of each of the individual 96 items separately and forecast their sourcing cost in June 2021. The dataset comprises of multiple values for the same month for the same product. However, simple time series based forecasting models utilise only one value to forecast the future values. Thus I have used aggregation functions to aggregate the values for each month.

Traditional steps of time series forecasting have been followed and applied on the 96 items for all the 5 aggregation functions used. The aggregation functions used are: arithmatic mean, minimum, maximum, median and trimmed mean. Outlier analysis for individual 96 items and for each month i.e. (96*12 interations) was computationally heavy and time consuming. Thus, a simple way to exclude outliers is utilised. I have used the trimmed mean function to exclude the initial and final few values, assuming they are outliers.

The following approach will be computationally efficient for large data and by applying parallel processing.

Section wise Description:
Imports: Import necessary Libraries

Load and explore data: Load training data and explore, convert it to necessary forms to solve the problem.

Visualize Time series and trends using decomposition of time series: Visualize the time series as well as the decomposed components, i.e. trends, seasonality and residue for all 96 items for all 5 aggregate functions. The additive model proved to describe the trend perfectly for the data.

Load Testing data: Load the test data and check if all 96 items are present. The test data has only 1 value for each of the unique item.

Check Stationarity: Check if time series are stationary before feeding them to the ARIMA model. All the time series for all items for all aggregation functions are stationary.

PACF Plots: Plots to visualise lags

ARIMA Forecasting: Forecast Values for June 2021 using ARIMA

Results: Analyse the performance of the model. Refer discussion part in the results section to know more about the result.
