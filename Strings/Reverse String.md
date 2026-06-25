# 344. Reverse String

## Problem

Write a function that reverses a string.

The input string is given as an array of characters `s`.

You must do this by modifying the input array in-place with O(1) extra memory.

**LeetCode Link:** https://leetcode.com/problems/reverse-string/

---

## Approach

Use the Two Pointers technique.

- Place one pointer at the beginning (`left`).
- Place another pointer at the end (`right`).
- Swap the characters at these positions.
- Move both pointers toward the center.
- Continue until they meet.

---

## Solution (Python)

```python
class Solution:
    def reverseString(self, s):
        left = 0
        right = len(s) - 1

        while left < right:
            s[left], s[right] = s[right], s[left]

            left += 1
            right -= 1
```

---

## Complexity Analysis

### Time Complexity

- O(n)

Each character is visited once.

### Space Complexity

- O(1)

The reversal is performed in-place.

---

## Example 1

### Input

```text
s = ["h","e","l","l","o"]
```

### Output

```text
["o","l","l","e","h"]
```

---

## Concepts Used

- Two Pointers
- Arrays
- In-Place Modification

---
