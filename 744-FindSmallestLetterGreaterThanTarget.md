# Find Smallest Letter Greater Than Target
- Given a list of sorted characters letters containing only lowercase letters, and given a target letter target, find the smallest element in the list that is larger than the given target.
- Letters also wrap around. For example, if the target is target = 'z' and letters = ['a', 'b'], the answer is 'a'.

## Linear Scan
O(n)
```python
def nextGreatestLetter(letters: List[str], target: str) -> str:
    for char in letters:
      if char > target:
        return char
    return None
```

## Binary Search
O(logn)
```python
def nextGreatestLetter(letters: List[str], target: str) -> str:
    length = len(letters)
    left = 0
    right = length -1

    while left <= right:
      middle = (left + right) // 2
      # Make left 1 index larger than target
      if letters[middle] == target:
        left = middle + 1
      elif letters[middle] < target:
        left = middle + 1
      elif letters[middle] > target:
        right = middle - 1
    # %: If left = lastIndex + 1, % returns 0 index
    return letters[left % length]
```