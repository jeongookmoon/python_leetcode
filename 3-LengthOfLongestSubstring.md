# Longest Substring Without Repeating Characters
- Given a string s, find the length of the **longest substring** **without repeating** characters.

### Note
* 1 loop using sliding window
* Test cases: pwwkew(start #3), dvdf(#2), ckilbkd(#3), tmmzuxt(#3)
* common pattern1: start = index of duplicate char + 1
* common pattern2: start must move right when duplicate char appears

## Sliding Window
O(n)
```python
def lengthOfLongestSubstring(s: str) -> int:
    # Sliding window
    seen = {}
    maxLength = start = 0
    
    for index, char in enumerate(s):
        # ['a', 'a', 'a']; index==1 => start < seen[char], index == 2 => start == seen[char]
        if char in seen and index and start <= seen[char]:
            start = seen[char]+1
        seen[char] = index
        maxLength = max(index-start+1, maxLength)
    
    return maxLength
```