# 14. Longest Common Prefix

## Problem

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.

**LeetCode Link:** https://leetcode.com/problems/longest-common-prefix/

---

## Approach

Use the first string as the initial prefix.

Iterate through the remaining strings:

- While the current string does not start with the prefix, remove the last character from the prefix.
- Continue until a common prefix is found.

If the prefix becomes empty, return `""`.

---

## Solution (Python)

```python
class Solution:
    def longestCommonPrefix(self, strs):
        ans = ""
        strs = sorted(stes)
        first = strs[0]
        last = strs[-1]
        if len(strs) == 0:
            return ans
        for i in range(len(strs)):
            if strs[i] == "":
                return  ans
        for j in range(min(len(first),len(last))):
            if first[i] != last[i]:
                return ans
            ans += ""
        return ans

```

---

## Complexity Analysis

### Time Complexity

- O(n × m)

Where:

- n = number of strings
- m = length of the shortest string

### Space Complexity

- O(1)

No extra data structures are used.

---

## Example 1

### Input

```text
strs = ["flower","flow","flight"]
```

### Output

```text
"fl"
```

---

## Example 2

### Input

```text
strs = ["dog","racecar","car"]
```

### Output

```text
""
```

---

## Concepts Used

- Strings
- Prefix Matching
- Iteration

---
