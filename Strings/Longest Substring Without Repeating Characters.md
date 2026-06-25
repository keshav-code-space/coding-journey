# 3. Longest Substring Without Repeating Characters

## Problem

Given a string `s`, find the length of the longest substring without repeating characters.

**LeetCode Link:** https://leetcode.com/problems/longest-substring-without-repeating-characters/

---

## Approach

Use the Sliding Window technique.

- Maintain a window using two pointers (`left` and `right`).
- Use a set to keep track of characters currently in the window.
- If a duplicate character is found, shrink the window from the left until the duplicate is removed.
- Update the maximum length at each step.

---

## Solution (Python)

```python
class Solution:
    def lengthOfLongestSubstring(self, s):
        char_set = set()

        left = 0
        max_length = 0

        for right in range(len(s)):

            while s[right] in char_set:
                char_set.remove(s[left])
                left += 1

            char_set.add(s[right])

            max_length = max(max_length, right - left + 1)

        return max_length
```

---

## Complexity Analysis

### Time Complexity

- O(n)

Each character is added and removed from the set at most once.

### Space Complexity

- O(min(n, m))

Where:

- n = length of string
- m = size of character set

---

## Example 1

### Input

```text
s = "abcabcbb"
```

### Output

```text
3
```

### Explanation

```text
"abc"
```

is the longest substring without repeating characters.

---

## Concepts Used

- Sliding Window
- Hash Set
- Two Pointers
- String Processing

---
