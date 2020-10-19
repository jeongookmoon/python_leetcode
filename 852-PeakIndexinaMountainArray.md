# Peak Index in a Mountain Array
- arr.length >= 3
- There is always a peak in arr. e.g. arr: [0, 2, 3, 1] peak: 2

## Iteration
O(n)
```python
class Solution:
    def peakIndexInMountainArray(self, arr: List[int]) -> int:
        for index in range(len(arr)):
            if arr[index] > arr[index+1]:
                return index
```