# House Robber
- You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security system connected and it will automatically contact the police if two adjacent houses were broken into on the same night.

- Given a list of non-negative integers representing the amount of money of each house, determine the maximum amount of money you can rob tonight without alerting the police.

### Note
* divide even/odd case to avoid consecutive index values
* take max in even/odd case to handle 2 indexes away case

## Dictionary Utilization
O(n)
```python
def rob(nums: List[int]) -> int:
    even = 0
    odd = 0

    for index in range(len(nums)):
      # even/odd case separation
      if index%2 == 0:
        # max for 2 indexes away case achieving the max
        even = max(even+nums[index], odd)
      else:
        odd = max(even, odd+nums[index])
    
    return max(even, odd)
```