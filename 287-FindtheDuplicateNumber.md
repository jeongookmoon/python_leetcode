# Find the Duplicate Number
- Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive.
- There is only one duplicate number in nums, return this duplicate number.

## Iteration
runtime: O(n) space: O(1)
```python
def findDuplicate(nums):
    for number in nums:
        if nums[abs(number)-1] < 0:
            return abs(number)
        else
            nums[abs(number)-1] *= -1
```

## Iteration
runtime: O(n) space: O(1)
```python
def findDuplicate(nums):
    # Find the intersection point of the two runners.
    tortoise = hare = nums[0]
    while True:
        tortoise = nums[tortoise]
        hare = nums[nums[hare]]
        if tortoise == hare:
            break
    
    # Find the "entrance" to the cycle.
    tortoise = nums[0]
    while tortoise != hare:
        tortoise = nums[tortoise]
        hare = nums[hare]
    
    return hare
```