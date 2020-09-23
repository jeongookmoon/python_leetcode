# Add Two Numbers
- Given a **non-empty** array of integers, every element appears twice except for one. Find that single one.

### Note
* Bit manipulation: same number cancel each other -> leftover is the answer

## Bit manipulation
O(n)
```python
def singleNumber(self, nums: List[int]) -> int:
  if(len(nums) > 0):
    result = nums[0]
    for index, each in enumerate(nums):
      if(index > 0):
        result ^= each
    return result
  else:
    return None
```

## Simpler
O(n)
```python
def singleNumber(self, nums: List[int]) -> int:
  result = 0
  for each in nums:
    result ^= each
  return result
```