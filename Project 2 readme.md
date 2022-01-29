# Using Machine Learning to Examine Portfolio Construction & Trading Performance in the Financial Marketplace

### Team Members

Michael Detwiler, Adnon Quaderi, Johnathan Boyle, Brandon Spadafora

## Our Goals for this Project

Our goal for this project was to examine how we could leverage machine learning in the financial markets to augment our trading performance. We decided to break this down into two separate examinations. 

The first would be a classfication study. We looked to answer whether our "machine" could group individual stocks better than ETFs currently trading in the marketplace. 

The second would be to build a forecasting model to detemine when to execute specific trades. We would also use this model to backtest potential historical returns based on our trading method.  

## Data Gathering, Cleanup, and API Selection

The first step for us to begin our project was to find historical stock data including a number of key metrics that would be used for both the clustering analysis and in building the machine learning model. We determined that metrics such as EBITDA, total debt, net income, VWAP, moving averages, etc. would be critical for us to perform our analysis.

Through various APIs and online resouces we were able to gather a data set of over 160 individual stocks inclduing the metrics mentioned above. This information would be used in the clustering analysis and in the forecasting model.

APIs used:

* Alpaca 
* IEX 

Online Resources used:

* Bloomberg
* Medium
* Github

![image](https://user-images.githubusercontent.com/91380617/151641968-779027d4-f22c-42c4-b60b-c3700d30fcb2.png)




## Analysis 1 - Clustering Study  









### Findings




## Analysis 2 - Machine Learning Model to Evaluate 

neural network technical analysis



### Findings


## Conclusion



### Challenges

1. Lack of available historical data (most of it is behind paywalls)
2. Lack of time 
3. General coding skills / getting different code to run

## Additional Thoughts / Continuation of Analysis

1. Would like to try the clustering analysis with a broader choice of stocks 
2. Would like to try the clustering analyis with more features (Financial metrics)
3. Backtest the forecasting model with additional stocks 
4. Run the forecast model with different technical analysis
6. Run both analyses for different asset classes

# References / Citations

https://towardsdatascience.com/silhouette-method-better-than-elbow-method-to-find-optimal-clusters-378d62ff6891

https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html

