# Longest Substring Without Repeating Characters
- Given a string s, find the length of the **longest substring** **without repeating** characters.

### Note
* 1 loop using sliding window
* Test cases: pwwkew(start #3), dvdf(#2), ckilbkd(#3), tmmzuxt(#3)
* common pattern1: start = index of duplicate char + 1
* common pattern2: start must move right when duplicate char appears

## Dictionary Utilization + Sliding Window
O(n)
```python
def lengthOfLongestSubstring(s: str) -> int:
  # Test cases:: pwwkew(start #3), dvdf(#2), ckilbkd (#3), tmmzuxt (#3)
  # base assumption: 1 loop -> sliding window
  # common pattern1: start = index of duplicate char + 1
  # common pattern2: start must move right when duplicate char appears

  usedSubStr = {}
  start = maxLength = 0

  for index, char in enumerate(s):
    # pattern1: start = index of duplicate char + 1
    if char in usedSubStr:

      # pattern2: start must move when duplicate char appears
      # 1. start might go left (start already passed duplicate character's index) -> no update if start > usedSubStr[char]
      # 2. start might not update when duplicate char appears if start == usedSubStr[char]
      if start < usedSubStr[char] or start == usedSubStr[char]:
        start = usedSubStr[char] + 1

    # add character to usedSubString dictionary
    usedSubStr[char] = index
    currentLength = index - start + 1

    # save maxLength
    maxLength = max(maxLength, currentLength)

    # print("char %s, index %s, start %s, maxLength %s" %(char, index, start, maxLength))
  return maxLength
```