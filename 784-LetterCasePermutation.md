# Letter Case Permutation
- Given a string S, we can transform every letter individually to be lowercase or uppercase to create another string.
- Return a list of all possible strings we could create. You can return the output in any order.

### Note
* 2 highlevel cases: albaphet vs number
* Within alphabet: lower vs upper

## Using DFS/Backtrack
runtime: O(2n) -> O(n). 56ms. Memory usage: 15.5 MB
```python
def letterCasePermutation(S: str) -> List[str]:
  def backtrack(sub='', index=0):
    if len(sub) == len(S):
      if sub not in result:
        result.add(sub)
    else:
      # alphabet + swapped case
      if S[index].isalpha():
        # Depth first
        backtrack(sub+S[index].swapcase(), index+1)
      # nonswapped + number case
      backtrack(sub+S[index], index+1)
  
  result = set()
  backtrack()
  return list(result)
```

## Using Loop
runtime: O(2n) -> O(n). **40ms**. Memory usage: **14.5 MB**
```python
def letterCasePermutation(S: str) -> List[str]
  result = ['']
  for char in S:
    # alphabet case
    if char.isalpha():
      # expand list by append char lower/upper cases
      result = [item+case for item in result for case in [char.lower(), char.upper()]]
    else:
      # append number for each item
      result = [item+char for item in result]
  return result
```