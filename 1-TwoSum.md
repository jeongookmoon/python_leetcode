# Two Sum
- Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
- You may assume that each input would have exactly one solution, and you may not use the same element twice.

### Note
* No "no answer" case
* No duplicate index answer

## Brute Force
O(n^2)
```python
def twoSumBruteForce(nums: List[int], target: int) -> List[int]:
  for i in range(len(nums)):
    for j in range(i+1, len(nums)):
      if nums[i]+nums[j] == target:
        return [i, j]
```

## Dictionary Utilization
1. Check two numbers in 1 loop -> use 2 data structures
2. Given: nums array + Add: dictionary
3. Use complement = target - nums[i] and save it in dictionary
4. Once complement of current number is found in dictionary, problem solved

O(n)
```python
def twoSumDictionary(nums: List[int], target: int) -> List[int]:
  # Will check dictionary + number in array together in one loop
  dictionary = {}
  for i in range(len(nums)):
    # Important: Target = currentNumber + complement
    currentNumber = nums[i]
    complement = target - currentNumber
    # If complement exist in dictionary, solution found.
    # because complement + currentNumber = target
    if complement in dictionary:
      return [dictionary[complement], i]
    else:
      dictionary[currentNumber] = i
```
