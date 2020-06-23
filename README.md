# Batch Time Series Forecasting using R and Prophet

TL;DR : Given a set of time series as input, this R script groups timeseries based on shared features and generates forecasts using Facebook's Prophet forecasting package.

### Processing Steps

* Remove activity from services that have not incurred a cost in the
last 30 days.
* Create features for each timeseries:
  * length of available time series data (short vs long)
  * avg daily cost for last 30 days (low vs high)
* Group timeseries data based on feature groupings:
  * high costs and long time series are forecasted individually.
  * high costs and short time series are forecasted together to improve accuracy.
  * low costs or short time series are forecasted together to improve accuracy.
* Anomaly Detection and Removal
* Generate forecasts for each forecasting group.
* Generate forecast accuracy scores using cross validation (Not
implemented.)