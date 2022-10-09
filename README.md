# data-mining-for-a-wine-sale-prediction
Imagine you’re a data scientist of an alcohol store (Cheers Alcohol) and your company is going to enter the market of Iowa. You are asked to design a go-to-market strategy based on the data you have. You need to suggest:<br>
1.If Cheers Alcohol wants to launch 3 stores, which county/counties should you target?<br>
2.To predict the total sales for the county/counties you selected to launch stores in each month of 2021<br>
3.What items would you sell in each store?  Select top 10 items in each store to promote<br>
And any other suggestions you will give for your go-to-market strategy after getting some insights from the data
<br>
<br>
original data link: **https://www.kaggle.com/datasets/sibmike/iowaliquorsales2020**



I only focus on the time series model part here, if wanna know more, the ppt file in repository is available.

## model part
three kinds of time series models are considered in this part,**ARIMA model**, **SARIMA model** , **Holt-winter model**.  <br>
repective model fitting performance show following.

### ARIMA
![image](https://github.com/ambiguousguy/data-mining-for-a-wine-sale-prediction/blob/main/pic/ARIMA.png)

**MSE:  842772226777.4719<br>
MAE:  790399.3286210742<br>
R square:  -0.41404394182537185**<br>
<br>
<br>
The prediction effect of the ARIMA model is not good, it cannot capture seasonal fluctuations well, (cannot fit peaks, and valleys), and the volatility of the data is not well represented in the last 15 months of forecasting.
<br>
<br>
### SARIMA
![image](https://github.com/ambiguousguy/data-mining-for-a-wine-sale-prediction/blob/main/pic/SARIMA.png)

**MSE:  469751950555.50354<br>
 MAE:  539458.8669184103<br>
 R square:  0.2118274917725167<br>**

<br>
<br>
SARIMA model can obviously better capture seasonal fluctuations, and it can also fully represent the seasonal fluctuations of data in the forecast segment. However, the capture of the peak has a certain delay.

<br>
<br>


For holt-winter model
<br>
![image](https://github.com/ambiguousguy/data-mining-for-a-wine-sale-prediction/blob/main/pic/holt.png)

**MSE:  300627793943.73114<br>
 MAE:  434423.96612776857<br>
 R square:  0.4955921691962636<br>**
<br>
<br>
Compare to the SARIMA model, Holt-winter can fit the peak and valley with better time delay, and obviously perform better than the SARIMA model.

