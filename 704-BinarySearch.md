# Add Two Numbers
- Given a sorted (in ascending order) integer array nums of n elements and a target value, write a function to search target in nums. If target exists, then return its index, otherwise return -1.

## Loop
O(LogN)
```python
def search(nums: List[int], target: int) -> int:
    left, right = 0, len(nums) - 1
    
    while left <= right:
        half = (left+right) // 2
    
        if nums[half] == target:
            return half
            
        elif nums[half] > target:
            right = half - 1
        
        else:
            left = half + 1
    
    return -1
```