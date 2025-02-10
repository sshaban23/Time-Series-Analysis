# Time-Series-Analysis

A1: RESEARCH QUESTION:

"How can we predict the daily revenue using historical data?"

A2: OBJECTIVES OR GOALS:

The main objective of this data analysis is to develop an accurate and reliable model to forecast daily revenue for the company using historical revenue data. By understanding and predicting revenue trends, the company can improve budgeting, resource allocation, and strategic planning. This analysis will help identify patterns and factors influencing revenue, which will help the company to make data-driven decisions and optimize its operations.

B: SUMMARY OF ASSUMPTIONS:

A key assumption is that the data is stationary, meaning its statistical properties, like mean and variance, remain constant over time. This helps in making the model's predictions more reliable. Also, time series models assume that data points are autocorrelated, meaning past values have a relationship with future values. This autocorrelation allows the model to use historical patterns to forecast future trends. Ensuring these assumptions are met is crucial for building an effective and accurate time series forecasting model.

C1: LINE GRAPH VISUALIZATION:

I first explored the dataset to understand its structure. I verified that there were no missing values or outliers that could distort our analysis. So, I did not have to clean the data since it is already ready for analysis.


![image](https://github.com/user-attachments/assets/7f6513ff-9cc5-4a70-8ae9-5bf407c05ed0)

C2: TIME STEP FORMATTING:

The time series data is recorded daily, with each day represented by an integer from Day 1 to Day 731, covering about two years. There are no gaps in the data, since each day has a corresponding revenue value. This consistent daily measurement makes the data well-suited for time series analysis.

C3: STATIONARITY:

To check if the time series data is stationary, I performed the Augmented Dickey-Fuller (ADF) test. The test results showed an ADF statistic of -1.9246 and a p-value of 0.3206, which is higher than the 0.05 threshold. This means we cannot reject the null hypothesis that the time series has a unit root, indicating the data is not stationary. For the time series to be suitable for modeling, I'll need to apply transformations like differencing to achieve stationarity.

C4: STEPS TO PREPARE THE DATA:

To prepare the data for analysis, I started by loading and exploring the dataset to understand its structure. I confirmed there were no missing values or outliers, and the data format was correct. I performed the Augmented Dickey-Fuller test to check for stationarity, which showed the data wasn't stationary initially. I then applied first-order differencing, which made the data stationary, as confirmed by the ADF test results. Finally, I split the data into training and test sets, with 80% of the data (584 days) used for training and 20% (147 days) for testing.

D1: REPORT FINDINGS AND VISUALIZATIONS:

Daily Revenue Time Series:
•	This graph shows the daily revenue over time, highlighting the general trend and any fluctuations in revenue.
Trend Component:
•	This graph displays the trend component extracted from the time series decomposition, indicating a clear upward trend in revenue over time.
Autocorrelation Function (ACF):
•	The ACF plot shows the correlation of the time series with its own past values, revealing significant autocorrelation at various lags.
Spectral Density:
•	The spectral density plot illustrates the power distribution across different frequencies, helping to identify dominant cycles or periodicities in the time series.
Decomposed Time Series:
•	This set of graphs shows the decomposed components of the time series: the original series, the trend, the seasonal component, and the residuals.
Residual Component:
•	The residuals plot from the decomposition shows the remaining variance after removing the trend and seasonal components, indicating the lack of any significant trends or patterns in the residuals.

D2: ARIMA MODEL:

I analyzed the data and determined that an ARIMA (2, 1, 2) model is appropriate. This model uses two autoregressive terms, first-order differencing to make the data stationary, and two moving average terms. The model fit well, as indicated by diagnostic tests, and it successfully captures the underlying patterns in the data, making it suitable for forecasting future revenue.

D3: FORECASTING USING ARIMA MODEL:


![image](https://github.com/user-attachments/assets/f95e9ce5-7da2-44e5-a5ff-d346d09bc905)


D4: OUTPUT AND CALCULATIONS:

The forecasted revenue for the next 30 days indicates a slight initial increase followed by stabilization. The revenue is expected to remain around 16.38 to 16.46 units. This consistent forecast suggests that after a small fluctuation, the revenue will level off, maintaining a steady value. This stability in the forecasted revenue can provide a reliable basis for short-term planning and decision-making, ensuring that expectations are aligned with projected financial performance.

E1: RESULTS:

Selection of an ARIMA Model:

I chose an ARIMA(2, 1, 2) model to analyze the time series data. This model was selected because it effectively captured the patterns in the data, including the trend and seasonality. The choice was based on observing the autocorrelation and partial autocorrelation functions of the differenced series, which indicated the need for two autoregressive and two moving average terms. This model fit the data well and was suitable for making accurate forecasts.

Prediction Interval of the Forecast:

The forecast for the next 30 days shows a slight increase in revenue initially, followed by stabilization around 16.38 to 16.46 units. The prediction interval provides a range within which the actual future values are expected to fall, considering the uncertainty of the forecast. This interval helps us understand the potential variability and offers a confidence range for our revenue predictions.


Justification of the Forecast Length:

I chose a 30-day forecast length because it provides a useful short-term projection for planning and decision-making. Forecasting for a longer period would introduce more uncertainty and be less reliable, while a shorter period might not give enough insight for strategic actions. A 30-day forecast strikes a good balance, offering actionable information with manageable uncertainty.

Model Evaluation Procedure and Error Metric:

To evaluate the model, I used the Akaike Information Criterion (AIC) and Bayesian Information Criterion (BIC), which are standard measures for comparing model fit. I also performed diagnostic checks like the Ljung-Box test and examined the residuals to ensure the model's assumptions were met and that the residuals looked like white noise. For assessing the forecast accuracy, I used error metrics like Mean Absolute Error (MAE) or Root Mean Squared Error (RMSE) to quantify the average errors between the observed and forecasted values. This helped in evaluating the model's predictive performance.

E2: ANNOTATED VISUALIZATION:


![image](https://github.com/user-attachments/assets/b077514f-3786-4230-9037-0153a0633aa6)

E3: RECOMMENDATION:
Given the results, our model is performing reasonably well with an MAE of 0.38 and an RMSE of 0.47, indicating that our forecasts are fairly accurate. Also, the high p-value from the Ljung-Box test suggests there’s no significant pattern left in the errors, meaning the model is likely capturing the data well. However, to ensure we continue to get the best results, we should periodically review and update the model, test it with more data, and consider exploring alternative models or adjustments if needed. Regular monitoring will help us maintain its accuracy and adapt to any changes over time.





















