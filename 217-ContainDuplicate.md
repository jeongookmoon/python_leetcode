# Add Two Numbers
- Given an array of integers, find if the array contains any duplicates.
- Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

### Note
* Seems good to use set

## Dictionary Utilization
O(n)
```python
def containsDuplicate(nums: List[int]) -> bool:
    thinSet = set()
    for eachNum in nums:
        if eachNum not in thinSet:
            thinSet.add(eachNum)
        else:
            return True
    return False
```