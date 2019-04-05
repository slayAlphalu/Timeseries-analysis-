# Timeseries-analysis-
## We try to analyze the time series trend by exploring the dataset AirPassengers.csv 从飞机乘客数据做时间序列分析


# Table of contents

### Q N A

**1.Import Libraries**

**2.Read Data**

**3.Data Transformation to achieve Stationarity**

**4.Log Scale Transformation**

**5.Exponential Decay Transformation**

**6.Time Shift Transformation**

**7.Plotting ACF & PACF**

**8.Building Models**

**9.Prediction & Reverse transformations**


**1. What is Time series analysis?**
A. Time Series is a series of observations taken at specified time intervals usually equal intervals. Analysis of the series helps us to predict future values based on previous observed values. In Time series, we have only 2 variables, time & the variable we want to forecast.

**2. Why & where Time Series is used?**
A. Time series data can be analysed in order to extract meaningful statistics and other charecteristsics. It's used in atleast the 4 scenarios:
a) Business Forecasting
b) Understand past behavior
c) Plan the future
d) Evaluate current accomplishment

**3. When shouldn't we use Time Series Analysis?**
A. We don't need to apply Time series in atleast the following 2 cases:
a) The dependant variable(y) (that is supposed to vary with time) is constant. Eq: y=f(x)=4, a line parallel to x-axis(time) will always remain the same.
b) The dependant variable(y) represent values that can be denoted as a mathematical function. Eq: sin(x), log(x), Polynomials etc. Thus, we can directly get value at some time using the function itself. No need of forecasting.

**4. What are the components of Time Series?**
A. There are 4 components:
a) Trend - Upward & downward movement of the data with time over a large period of time. Eq: Appreciation of Dollar vs rupee.
b) Seasonality - seasonal variances. Eq: Ice cream sales increases in Summer only
c) Noise or Irregularity - Spikes & troughs at random intervals
d) Cyclicity - behavior that repeats itself after large interval of time, like months, years etc.

**5. What is Stationarity?**
A. Before applying any statistical model on a Time Series, the series has to be staionary, which means that, over different time periods,
a) It should have constant mean.
b) It should have constant variance or standard deviation.
c) Auto-covariance should not depend on time.

**Trend & Seasonality are two reasons why a Time Series is not stationaru & hence need to be corrected.**

**6. Why does Time Series(TS) need to be stationary?**
A. It is because of the following reasons:
a) If a TS has a particular behavior over a time interval, then there's a high probability that over a different interval, it will have same behavior, provided TS is stationary. This helps in forecasting accurately.
b) Theories & Mathematical formulas ae more mature & easier to apply for as TS which is stationary.

**7. Tests to check if a series is stationary or not**
A. There are 2 ways to check for Stationarity of a TS:
a) Rolling Statistics - Plot the moving avg or moving standard deviation to see if it varies with time. Its a visual technique.
b) ADCF Test - Augmented Dickey–Fuller test is used to gives us various values that can help in identifying stationarity. The Null hypothesis says that a TS is non-stationary. It comprises of a Test Statistics & some critical values for some confidence levels. If the Test statistics is less than the critical values, we can reject the null hypothesis & say that the series is stationary. THE ADCF test also gives us a p-value. Acc to the null hypothesis, lower values of p is better.

**8. What is ARIMA model?**
A. ARIMA(Auto Regressive Integrated Moving Average) is a combination of 2 models AR(Auto Regressive) & MA(Moving Average). It has 3 hyperparameters - P(auto regressive lags),d(order of differentiation),Q(moving avg.) which respectively comes from the AR, I & MA components. The AR part is correlation between prev & current time periods. To smooth out the noise, the MA part is used. The I part binds together the AR & MA parts.

**9. How to find value of P & Q for ARIMA ?**
A. We need to take help of ACF(Auto Correlation Function) & PACF(Partial Auto Correlation Function) plots. ACF & PACF graphs are used to find value of P & Q for ARIMA. We need to check, for which value in x-axis, graph line drops to 0 in y-axis for 1st time.
From PACF(at y=0), get P
From ACF(at y=0), get Q

**10. What Is ADCF test?**
A. In statistics and econometrics, an augmented Dickey–Fuller test (ADF) tests the null hypothesis that a unit root is present in a time series sample. The alternative hypothesis is different depending on which version of the test is used, but is usually stationarity or trend-stationarity. It is an augmented version of the Dickey–Fuller test for a larger and more complicated set of time series models.
The augmented Dickey–Fuller (ADF) statistic, used in the test, is a negative number. The more negative it is, the stronger the rejection of the hypothesis that there is a unit root at some level of confidence.
p value(0<=p<=1) should be as low as possible. Critical values at different confidence intervals should be close to the Test statistics value.

**11. What is Exponential Smoothing?**
A. Exponential smoothing is a rule of thumb technique for smoothing time series data using the exponential window function. Whereas in the simple moving average the past observations are weighted equally, exponential functions are used to assign exponentially decreasing weights over time. It is an easily learned and easily applied procedure for making some determination based on prior assumptions by the user, such as seasonality. Exponential smoothing is often used for analysis of time-series data.
The raw data sequence is often represented by xt,beginning at time  t=0, 
and the output of the exponential smoothing algorithm is commonly written as  st, which may be regarded as a best estimate of what the next value of  x
will be. When the sequence of observations begins at time  t=0,
the simplest form of exponential smoothing is given by the formulas:

s0=x0
st=α∗xt+(1−α)∗st−1,  t>0 where  α is the smoothing factor, and  0<α<1.

**12. What is Exponential decay?**
A. A quantity is subject to exponential decay if it decreases at a rate proportional to its current value. 
Symbolically, this process can be expressed by the following differential equation, where N is the quantity and λ (lambda) is a positive rate called the exponential decay constant:
dN/dt=−λN
 
The solution to this equation (see derivation below) is:
N(t)=N0∗e−λt
where N(t) is the quantity at time t, and N0 = N(0) is the initial quantity, i.e. the quantity at time t = 0.
Half Life is the time required for the decaying quantity to fall to one half of its initial value. 
It is denoted by  t1/2. The half-life can be written in terms of the decay constant as: t1/2=ln(2)/λ

The content is from [Kaggle](https://www.kaggle.com/freespirit08/time-series-for-beginners-with-arima)
 
