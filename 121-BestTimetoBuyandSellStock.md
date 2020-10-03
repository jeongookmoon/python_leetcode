# Best Time to Buy and Sell Stock
- Say you have an array for which the ith element is the price of a given stock on day i.
- If you were only permitted to complete at most one transaction (i.e., buy one and sell one share of the stock), design an algorithm to find the maximum profit.
- Note that you cannot sell a stock before you buy one.

### Note
* maxProfit with a buy = subSum
* because (p[1]-p[0]) + ([p2]-p[1]) = [p2] - [0]
* if lower buy appears, subSum = -, so reset subSum = 0
* maxProfit in the array = subSum max

## Loop
O(n)
```python
def maxProfit(prices: List[int]) -> int:
  subSum, subSumMax = 0, 0
  for index in range(1, len(prices)):
    # find subSum
    subSum += prices[index] - prices[index-1]
    # reset to 0 
    subSum = 0 if subSum < 0 else subSum

    subSumMax = max(subSum, subSumMax)
  return subSumMax
```