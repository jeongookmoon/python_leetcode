# Missing Number
- Given an array of integers where 1 ≤ a[i] ≤ n (n = size of array), some elements appear twice and others appear once.
- Find all the elements of [1, n] inclusive that do not appear in this array.
- Could you do it without extra space and in O(n) runtime? You may assume the returned list does not count as extra space.

### Note
* No extra space
* Duplicate integer shows missing integer in index

## Using Set
runtime: O(n), space: O(2*(n+1))=>O(n)

```python
def missingNumber(self, nums: List[int]) -> int:
# Negate integers using each interger as index
  for index, value in enumerate(nums):
    # Since integer starts from 1, minus 1 to use it as index
    # Absolute value to avoid double negate
    valueIndex = abs(value)-1
    nums[valueIndex] = -abs(nums[valueIndex])
# Missing integer = index+1 with positive integer
  answer = []
  for index in range(len(nums)):
    if nums[index] > 0:
      answer.append(index + 1)
  return answer
```
