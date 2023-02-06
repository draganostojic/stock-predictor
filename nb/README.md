<p align = "center" draggable=”false” ><img src="https://user-images.githubusercontent.com/37101144/161836199-fdb0219d-0361-4988-bf26-48b0fad160a3.png" 
     width="200px"
     height="auto"/>
</p>

# Stock Prophet 


## Task 3. Routes


Q: What happens if the input ticker doesn't have a trained model or the ticker is not valid?

A: If the input ticker doesn't have a trained model or the ticker is not valid we get the following reply:

{"detail":"Model not found."}


## Task 4. AWS Deployment


This is the command to retrieve the prediction from my instance of EC2:

    ```
    $ curl \
    --header "Content-Type: application/json" \
    --request POST \
    --data '{"ticker":"MSFT", "days":7}' \
    http://ec2-54-200-219-49.us-west-2.compute.amazonaws.com:8000/predict


    {"ticker":"MSFT","days":7,"forecast":{"02/07/2023":229.4357514883677,"02/08/2023":229.27908570247922,"02/09/2023":229.12241991659073,"02/10/2023":228.9657541307022,"02/11/2023":228.80908834481372,"02/12/2023":228.65242255892517,"02/13/2023":228.49575677303667}}
    ```

This is a link for documentation on my EC2 instance


    ```
    http://ec2-54-200-219-49.us-west-2.compute.amazonaws.com:8000/docs

    ```

## Answers to Questions

Algorithm Understanding
Q: How does the Prophet Algorithm differ from an LSTM?
A: Long short-term memory (LSTM) gives prediction based on single points and by previous sequence of data of a certain length. Prophet is built to predict business time series including seasonality and trend.

Q: Why does an LSTM have poor performance against ARIMA and Profit for Time Series?
A: LSTM hzs poor performance compared to ARIMA and Prophet mainly because it is a more general prediction
 tool which works best on high volume of data so it's prone to overfitting when the set is relatively small. It also requires careful tuning of hyperparamters to make it work.

This criterion is linked to a Learning Outcome Interview Readiness

Q: What is exponential smoothing and why is it used in Time Series Forecasting?
A: It is a method of smooting time series data using exponential window function which assings exponentially
decreasing weights over time.

This criterion is linked to a Learning Outcome Interview Readiness
Q: What is stationarity? 
A: Stationarity means that mean, variance and autocorrelation is not changing over time. Put it another way
time series looks with constant variance and without periodic fluctuations.

Q: What is seasonality? 
A: Sesasonality is opposite of stationarity. It represents periodic fluctations in time series.

Q: Why Is Stationarity Important in Time Series Forecasting?
A: Most time series models assume stationarity


This criterion is linked to a Learning Outcome Interview Readiness

Q: How is seasonality different from cyclicality? Fill in the blanks:
___ is predictable, whereas ___ is not.
A: Seasonality is predictable whereas cyclicality is not. Sesonality is with predictable and unchanging frequency while cyclicality is not.
