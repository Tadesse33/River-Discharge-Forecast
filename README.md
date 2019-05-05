**River-Discharge-Forecast**

**Background**

River discharge (streamflow) prediction is essential in many applications, such as to evaluate water quality and to determine flood risks. In rivers and streams that receive partially treated wastewater, the flow magnitude is critical information to establish effluent discharge permit. During the high streamflow period, the effluent will be diluted more and expected to minimize the immediate environmental impact of affluent constituents. However, the effluent is less diluted during the low streamflow period and aquatic life will be more exposed to effluent chemicals. For this reason, water quality regulation requires effluent discharge permit to be evaluated based on the low flow season.

The U.S. Environmental Protection Agency designates the one day (1Q10) or seven days (7Q10) average lowest streamflow that occurs once in every 10 years as the protective design low flow. The design low flow is determined commonly using DFLOW 3.0 program that uses statistical frequency analysis on historical river discharge records, which assumed that the long term (10 years in this case) averages remain constant. However, studies showed that the hydrological flow regime can change when there is a shift in periodicity of precipitation and land use modifications. 

In this project, river discharge is forecasted for Yakima River, Washington to account for future flow regime changes. This project is part of the bigger Yakima project aimed at understanding effluent mixing and dilution in a restored floodplain.
Two modeling techniques that were successfully applied to forecast patterns in various domain areas are implemented, namely, Long Short-Term Memory (LSTM) from deep learning and Autoregressive Integrated Moving Average (ARIMA) from statistical models. 

**Methodology** 

1.	[Clean and transform data](http://localhost:8888/notebooks/Desktop/WorkingDirectory/DataScience/Own_Projects/Flow_Analysis/Part%20I--Clean%20and%20Transform%20Data.ipynb) 
+ River flow records were collected from USGS gauge for a record from 1966 to 2019. 
2.	Select error metrics
    MASE (mean absolute scaled error)- compare the mean absolute error of the model to the naive forecast
    MAPE (mean absolue percent error) - the percentage of the forecast error compared to the observed value
    RMSE (root mean squared error) - the squared difference between the observed and forecasted values, finds the average, and then finds the square root

3.	[Fit and validate ARIMA model](http://localhost:8888/notebooks/Desktop/WorkingDirectory/DataScience/Own_Projects/Flow_Analysis/Part%20II--Forecast%20Discharge%20with%20ARIMA%20Model.ipynb) 
4.	[Train and validate LSTM network](http://localhost:8888/notebooks/Desktop/WorkingDirectory/DataScience/Own_Projects/Flow_Analysis/Part%20III---Forecast%20Discharge%20with%20LSTM.ipynb)

**Conclusion**

The performance of ARIMA and LSTM is compared in river flow forecast. These methods were implemented in two scenarios, forecast using all seasons record (12 months) and using the lowest flow season daily record (January). On all season time series, LSTM prediction accuracy was superior to ARIMA (refer the ARIMA dynamic forecast case. The one-step-forecast performance is not compared as it was trained with all data). The use of January time series improved the prediction accuracy of the two methods. From this preliminary result, we can conclude that LSTM method is an effective method for forecasting river flow. The proposed method can be applied in other regions with similar environmental setup. In order to improve the prediction accuracy to the desired level, advanced hyperparameter tuning with a higher number of river flow data is suggested. 
