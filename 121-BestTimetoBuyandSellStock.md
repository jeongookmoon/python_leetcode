# Best Time to Buy and Sell Stock
- Say you have an array for which the ith element is the price of a given stock on day i.
- If you were only permitted to complete at most one transaction (i.e., buy one and sell one share of the stock), design an algorithm to find the maximum profit.
- Note that you cannot sell a stock before you buy one.

### Note
* 2 cases between i and i+1: prices[i+1]-prices[i] = **positive** or (negative or 0)
* 2 cases for positive case in each i+1: **greater** or (less difference)
* (prices[1] - prices[0]) + (prices[2] - prices[1]) + (prices[3] - prices[2]) = prices[3] - prices[0]