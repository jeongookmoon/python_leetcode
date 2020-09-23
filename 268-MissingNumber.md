# Missing Number
- Given an array containing n distinct numbers taken from 0, 1, 2, ..., n, find the one that is missing from the array.

### Note
* Length of array replaces missing number
* Must be in O(n) for runtime, O(1) for extra space complexity

## Using Set
runtime: O(n), space: O(2*(n+1))=>O(n)
```python
def missingNumber(self, nums: List[int]) -> int: 
  # make set of numbs array
  dataSet = set(nums)
  # visit 0 to length n index to find out missing number
  for index in range(nums):
    if index not in dataSet:
      return index
```

## Using Bit Manipulation
runtime: O(n), space: O(n)
```python
def missingNumber(self, nums: List[int]) -> int:
  # main idea: XOR same number -> 0
  # length of array n replaced the missing number
  # n=2, 2^(0^0)^(1^2) -> (0^0)^(2^2)^1 -> 1
  missing = len(nums)
  for index, eachNum in enumerate(nums):
    missing ^= index ^ eachNum
  return missing
```