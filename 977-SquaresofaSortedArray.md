# Squares of a Sorted Array
- Given an array of integers A sorted in non-decreasing order, return an array of the squares of each number, also in sorted non-decreasing order.

### Note
* 1 <= A.length <= 10000
* -10000 <= A[i] <= 10000
* A is sorted in non-decreasing order.

## Using two pointers
Time: O(n), Space: O(n)
```python
def sortedSquares(A: List[int]) -> List[int]:
  answer, left, right = [0]*len(A), 0, len(A)-1
  index = right

  while left <= right:
    leftAbs, rightAbs = abs(A[left]), abs(A[right])
  
    if leftAbs > rightAbs:
      answer[index] = leftAbs*leftAbs
      left += 1
    else:
      answer[index] = rightAbs*rightAbs
      right -= 1
    index -= 1

  return answer
```
