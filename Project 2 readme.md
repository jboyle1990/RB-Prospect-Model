# Using Machine Learning to Examine Portfolio Construction & Trading Performance in the Financial Marketplace

### Team Members

Michael Detwiler, Adnon Quaderi, Johnathan Boyle, Brandon Spadafora

## Our Goals for this Project

Our goal for this project was to examine how we could leverage machine learning in the financial markets to augment our trading performance. We decided to break this down into two separate examinations. 

The first would be a classfication study. We looked to answer whether our "machine" could group individual stocks better than ETFs currently trading in the marketplace. 

The second would be to build a forecasting model to detemine when to execute specific trades. We would also use this model to backtest potential historical returns based on our trading method.  

## Data Gathering, Cleanup, and API Selection

The first step for us to begin our project was to find historical stock data including a number of key metrics that would be used for both the clustering analysis and in building the forecasting model. We determined that metrics such as EBITDA, total debt, net income, VWAP, moving averages, etc. would be critical for us to perform our analysis.

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





### Elbow Curve



![image](https://user-images.githubusercontent.com/91380617/151642273-4a1d0736-d472-4153-940a-e4b9e7978325.png)

### Sihlouette Analysis 



### Findings




## Analysis 2 - Machine Learning Model to Evaluate 


### Model Features

![image](https://user-images.githubusercontent.com/91380617/151642334-b34b27e9-3bbd-4020-9baa-f7dfcbf292b3.png)

### Model Evaluation


![image](https://user-images.githubusercontent.com/91380617/151642357-1efd6bf9-d472-4f72-823a-5d651eab5d7a.png)


![image](https://user-images.githubusercontent.com/91380617/151642374-59ea47e1-5771-4c9e-aa0c-37720f941843.png)


![image](https://user-images.githubusercontent.com/91380617/151642382-1cc09a85-9f14-4f52-a141-7bc953a93a7d.png)


![image](https://user-images.githubusercontent.com/91380617/151642389-e3419b09-d7cc-45a8-bfe2-0243aa0a0870.png)


![image](https://user-images.githubusercontent.com/91380617/151642396-b50d56c2-a060-46e0-b0d6-7743f09d29e8.png)




### Findings


![image](https://user-images.githubusercontent.com/91380617/151642410-97aec5b9-9be8-4978-935e-6a9faa339fe1.png)


![image](https://user-images.githubusercontent.com/91380617/151642416-6fd04200-5d8e-4051-b596-65729cccd930.png)


## Conclusion



### Challenges

1. Lack of available historical data (most of it is behind paywalls)
2. Lack of time 
3. General coding skills / getting different code to run
4. Learning how to use a new API
5. Learnign a clustering method

## Additional Thoughts / Continuation of Analysis

1. Would like to try the clustering analysis with a broader choice of stocks 
2. Would like to try the clustering analyis with more features (Financial metrics)
3. Backtest the forecasting model with additional stocks 
4. Run the forecast model with different technical analysis
6. Run both analyses for different asset classes

# References / Citations

https://towardsdatascience.com/silhouette-method-better-than-elbow-method-to-find-optimal-clusters-378d62ff6891

https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html

