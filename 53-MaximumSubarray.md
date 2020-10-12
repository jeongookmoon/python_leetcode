# Maximum Subarray
- Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.
- Follow up: If you have figured out the O(n) solution, try coding another solution using the divide and conquer approach, which is more subtle.


## Note
- If previous sum < 0, better to start finding sum from current index

## Loop
O(n)
```python
def maxSubArray(nums: List[int]) -> int:
    if len(nums) == 0:
        return None

    maxSum = nums[0]

    for index in range(1, len(nums)):
        nums[index] += nums[index-1] if nums[index-1] > 0 else 0
        maxSum = nums[index] if nums[index] > maxSum else maxSum
        
    return maxSum
```
