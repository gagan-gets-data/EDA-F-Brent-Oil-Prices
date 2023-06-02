# EDA and Forecasting Brent Oil Prices
Dataset - https://raw.githubusercontent.com/rajeevratan84/data-analyst-bootcamp/master/BrentOilPrices.csv

This analysis study is on Brent Oil Prices and attempt on forecasting future prices **using Prophet and ARIMA models**.

## Visualizing Full Data as a line plot
![24](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/e0519eaa-cced-4c5f-8428-17ed8bd1c7fa)

## Analysis using Prophet Model

Here we can understand that on the basis of above data on generating forecast for the next 90 days, there are different components to look into : trend, weakly and yearly seasonality - and for each of these components, we have the lower and upper confidence intervals data. 

![25](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/90784bed-d00e-4994-9e52-ebe9ca2ebf76)

- A single forecast plot
![28](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/e124004a-234c-438c-8717-ae043db73dc5)

## Side-by-side comparison of original data and forecast between 2017-01-01 and 2020-01-01
![30](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/00f949b7-ae9a-4223-83a9-a60541c7582d)

## Using ARIMA Model
Checking the stationarity of the time series using Augmented Dickey - Fuller Test
![31](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/8754a874-b6c8-4fbd-9a28-d458243750e6)
![32](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/6e283054-3759-4612-b147-f95c83379578)

**Observation** - The null hypothesis of ADF test is the Time series is NOT stationary. We see that the Test Statistic (-1.95) is higher than 10% Critical Value (-2.56). This means this result is statistically significant at 90% confidence interval and so, we fail to reject the null hypothesis.

**This means that our time series data is NOT stationary.**

**Implementing Autocorrelation Function and Partial Correlation Function**
![33](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/3a384c4d-e187-4ae1-ad78-2f7bfb56f6a5)

![34](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/3d6ef6a9-cff1-4178-9c41-c3d93d40719d)

**Converting time series data to stationary**

- Taking Log Transform
![35](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/c428160e-45c6-4e59-9aed-6c638d277501)

- Moving average of last 12 values
![36](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/db93afcf-a8e4-4791-bbe9-ec4d492bc63d)

- Differencing
![37](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/4a7f4892-6cd8-44a2-87d1-63260e448f2d)

Testing again using Augmented Dickey - Fuller Test
![38](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/ef518214-5ebf-4e99-b6a8-a2d5cb6866b4)
![39](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/21813e1a-e68b-427c-bb2d-3af09836c2cb)

Taking Exponentially weighted moving averages as well -
![40](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/8e7a6a13-0d73-418f-b9b6-0122b845e24d)
![41](https://github.com/gagan-gets-data/EDA-F-Brent-Oil-Prices/assets/134737002/c8fccf71-3c8d-4f18-8c16-4931761b845c)

