# Find All Duplicates in an Array
- Given an array of integers, 1 ≤ a[i] ≤ n (n = size of array), some elements appear twice and others appear once.
- Find all the elements that appear twice in this array.
- Could you do it without extra space and in O(n) runtime?

## Iteration
runtime: O(n) space: O(1)
```python
def findDuplicates(nums: List[int]) -> List[int]:
    result = []
    for number in nums:
      if nums[abs(number)-1] < 0:
        result.append(abs(number))
      else:
        nums[abs(number)-1] *= -1
```