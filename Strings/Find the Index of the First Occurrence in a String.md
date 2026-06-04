# 28. Find the Index of the First Occurrence in a String

## Problem

**LeetCode Link:** https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/

---

## Approach

Use a sliding window over `haystack`.

For each possible starting position:

1. Extract a substring of length `len(needle)`.
2. Compare it with `needle`.
3. If they match, return the current index.

If no match is found, return `-1`.

---

## Solution (Python)

```python
class Solution:
    def strStr(self, haystack, needle):
        n = len(haystack)
        m = len(needle)

        for i in range(n - m + 1):
            if haystack[i:i + m] == needle:
                return i

        return -1
```

---

## Complexity Analysis

### Time Complexity

- O((n - m + 1) × m)

Where:

- n = length of haystack
- m = length of needle

In the worst case, we compare m characters for each starting position.

### Space Complexity

- O(1)

Ignoring the temporary substring created by slicing.

---

## Example 1

### Input

```text
haystack = "sadbutsad"
needle = "sad"
```

### Output

```text
0
```

---

## Concepts Used

- Strings
- Sliding Window
- Pattern Matching

---
