# 58. Length of Last Word

## Problem

Given a string `s` consisting of words and spaces, return the length of the last word in the string.

A word is a maximal substring consisting of non-space characters only.

**LeetCode Link:** https://leetcode.com/problems/length-of-last-word/

---

## Approach 1: Traverse from the End

Start from the last character:

1. Skip trailing spaces.
2. Count characters until another space is encountered.
3. Return the count.

This avoids creating extra strings.

---

## Solution (Python)

```python
class Solution:
    def lengthOfLastWord(self, s):
        i = len(s) - 1

        while i >= 0 and s[i] == " ":
            i -= 1

        length = 0

        while i >= 0 and s[i] != " ":
            length += 1
            i -= 1

        return length
```

---

## Complexity Analysis

### Time Complexity

- O(n)

In the worst case, we scan the string once.

### Space Complexity

- O(1)
- O(n) - for Approach 2

No extra data structures are used.

---

## Approach 2: Using split()

```python
class Solution:
    def lengthOfLastWord(self, s):
        return len(s.split()[-1])
```

---

## Example 1

### Input

```text
s = "Hello World"
```

### Output

```text
5
```

---

## Concepts Used

- Strings
- Two Pointers
- Reverse Traversal

---
