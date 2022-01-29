# Using Machine Learning to Examine Portfolio Construction & Trading Performance in the Financial Marketplace

### Team Members

Michael Detwiler, Adnan Quaderi, Johnathan Boyle, Brandon Spadafora

## Our Goals for this Project

Our goal for this project was to examine how we could leverage machine learning in the financial markets to augment our trading performance. We decided to break this down into two separate examinations. 

The first would be a classfication study. We looked to answer whether our "machine" could group individual stocks better than ETFs currently trading in the marketplace. 

The second would be to build a forecasting model to detemine when to execute specific trades. We would also use this model to backtest potential historical returns based on our trading method.  

## Data Gathering, Cleanup, and API Selection

The first step for us to begin our project was to determine the stocks that we would use for our dataset. We realized that we needed a large pool of individual stock data and settled on the number of stocks in the 150+ range. The high number of stocks was important to us because we wanted to provide our clustering code a large and rich dataset to analyze.

To save time we decided to pull stocks from established ETFs across three distinct sectors (tech, consumer staples, and utilities).

The next step was to find historical stock data including a number of key metrics that would be used for both the clustering analysis and in building the forecasting model. We determined that metrics such as EBITDA, total debt, net income, VWAP, moving averages, etc. would be critical for us to perform our analysis.

Through various APIs and online resouces we were able to gather a data set of over 160 individual stocks inclduing the metrics mentioned above. This information would be used in the clustering analysis and in the forecasting model.

APIs used:

* Alpaca 
* IEX 

Online Resources used:

* Bloomberg
* Medium
* Github

Once we gathered the historical data (including financial metrics) and saved in a dataframe the output looked like the below:

![image](https://user-images.githubusercontent.com/91380617/151641968-779027d4-f22c-42c4-b60b-c3700d30fcb2.png)


## Analysis 1 - Clustering Study  

The clustering analysis is a crucial part of our study as we're treating this as a  way to construct a future portfolio. Our goal here is to identify cross-sector groupings and to identify optimal clusters.

### Elbow Curve

Observing the elbow curve there was a very distinct breaking point at 2 clusters with a second, less distinct, breaking point at 5 clusters.

![image](https://user-images.githubusercontent.com/91380617/151642273-4a1d0736-d472-4153-940a-e4b9e7978325.png)


### Sihlouette Analysis 

The sihlouette score is much higher for 2 clusters than any other grouping telling us that two clusters is the optimal number. 

![Silhouette Score vs  Number of Clusters](https://user-images.githubusercontent.com/91380617/151643216-d9708ac4-d124-45c2-a51f-93e95f4c80b9.png)

It's intersting that the second highest silhouette score is at 9 clusters. It's a wide spread of the two highest sihouette scores and a very flat distribution of clusters 3 through 8. 

### Findings

Both methods to identify the optimal number of clusters determined that number was 2. With leanings toward a much higher number for the second best number of clusters.

A major discovery when analyzing the optimal number of clustered groups was that Facebook, Apple, Amazon, Netflix and Google (FAANG) were put into a group. These stocks were identified as as outliers and grouped together when the remaining 155 stocks formed the second cluster. We viewed this as a significant achievement for the model / code as there are FAANG traded ETFs in the marketplace.  

Our interpretation of the data was that because we pulled from ETFs the group of stocks were too similar for the machine to separate.

In the future we would like to introduce different data to the algorithm such as:

* stocks outside these specific ETFs
* different asset classes
* different features )more financial metrics)

## Analysis 2 - Forecasting with our Trading Method 

The second part of our analysis was building a forecasting model to predict underlying stock price and evaluate potential returns from our forecasts. We would also analyze our forecasted based trading against a technical trading strategy (moving average crossover).

### Model Specifications:

Here are the features of our RNN LSTM model:

* 3 Layers
* Dropout fraction of 20%
* Model was compiled using the adam optimizer
* Mean square error was used as the loss function 
* Used Early stopping as a new feature to determine the number of Epochs used

![image](https://user-images.githubusercontent.com/91380617/151642334-b34b27e9-3bbd-4020-9baa-f7dfcbf292b3.png)

Model Training Process:

* Takes less than a minute to scale, train, compile & fit
* window size of 50
* 200 nuerons 
* batch size of 64
* time series length of 5-7 years
* 70% of the data was used for training

## Trading Strategy

Directional and always invested. Our two potential trades are 1M shares long or 1M shares short. We will examine both a technical analysis strategy and a strategy based off technical analysis.

1. Technical Analysis Trading -  If short moving average is greater than long moving average then stay or go long. 
2. LSTM Driven Trading - we will trade on the predicted price of underlying asset

### Model Evaluation

Here are the various model outputs throughout the model's use and in our analysis:

![image](https://user-images.githubusercontent.com/91380617/151642357-1efd6bf9-d472-4f72-823a-5d651eab5d7a.png)


![image](https://user-images.githubusercontent.com/91380617/151642374-59ea47e1-5771-4c9e-aa0c-37720f941843.png)


![image](https://user-images.githubusercontent.com/91380617/151642382-1cc09a85-9f14-4f52-a141-7bc953a93a7d.png)


![image](https://user-images.githubusercontent.com/91380617/151642389-e3419b09-d7cc-45a8-bfe2-0243aa0a0870.png)


![image](https://user-images.githubusercontent.com/91380617/151642396-b50d56c2-a060-46e0-b0d6-7743f09d29e8.png)


### Analyzing Trading Performance

* Technical based trading has more outliers on the negative side
* This is consistent with the long term performance seen in graph above

* LSTM trading outperformed technical trading strategy

![image](https://user-images.githubusercontent.com/91380617/151642410-97aec5b9-9be8-4978-935e-6a9faa339fe1.png)

![image](https://user-images.githubusercontent.com/91380617/151642416-6fd04200-5d8e-4051-b596-65729cccd930.png)

### Findings

1. Running longer time series analysis to 2009 yields poor results 
2. Model can generate good forecast if parameters are properly optimized
3. Expect a continual process to maintain optimal forecast and profitable strategy
4. LSTM forecast driven strategy outperformed moving average strategy

### Challenges

1. Lack of available historical data (most of it is behind paywalls)
2. Lack of time 
3. General coding skills / getting different code to run
4. Learning how to use a new API
5. Learning a clustering method

## Additional Thoughts / Continuation of Analysis

1. Would like to try the clustering analysis with a broader choice of stocks 
2. Would like to try the clustering analyis with more features (Financial metrics)
3. Backtest the forecasting model with additional stocks (up to 1000)
4. Run the forecast model against different technical analysis
6. Run both analyses for different asset classes
 

# References / Citations

https://towardsdatascience.com/silhouette-method-better-than-elbow-method-to-find-optimal-clusters-378d62ff6891

https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html

