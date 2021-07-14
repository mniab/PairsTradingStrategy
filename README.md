# PairsTradingStrategy
Pairs trading is a strategy in which we use various statistical methods to  pair-up 2 stocks whose prices have moved together in the past and are potentially market neutral. We monitor the spread between the prices and when these prices diverge, we short the winner and buy the loser. The paper can be read from [here ](https://www.researchgate.net/publication/227624374_Pairs_Trading).

![alt](./images/PTS_unt.jpg)
 

There are two approaches:
1. The distance approach, it is a very straight foward approach for selecting stocks for pair trading. 
Suppose we are considering stock prices of ‘n’ different companies. This approach uses the euclidean distance between normalized stock prices as a metric to check if the two stocks are closely related to each other.
For every pair of stocks we calculate  the sum of squared Euclidean distance between the normalized prices at each time frame. 

![alt](./images/disap1.jpg)
![alt](./images/disap2.jpg)
![alt](./images/disap3.jpg)

2. Cointegration approach, it is a statistical property of a collection of time series variables which allow dynamic modelling of non stationary time series sharing a common stochastic trend.
Let assume two stocks X and Y whose values varies with time and give us two time series stock. Both of them are stationary at first difference i.e. of I(1) form and if possible we can choose a constant value say β0 such that if linear combination of X and Y are stationary then we can say series are cointegrated.

![alt](./images/coinap.jpg)

And we use the p-values to find out the cointegration
The p-value is the probability of obtaining results at least as extreme as the observed results of a statistical hypothesis test, assuming that the null hypothesis is correct. The p-value is used as an alternative to rejection points to provide the smallest level of significance at which the null hypothesis would be rejected. A smaller p-value means that there is stronger evidence in favor of the alternative hypothesis.
If the pvalue is small, below a critical size (0.05 in our case), then we can reject the hypothesis that there is no cointegrating relationship. The smaller the p-value, stocks will be that much well cointegrated.

