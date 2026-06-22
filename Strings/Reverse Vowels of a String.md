# 345. Reverse Vowels of a String

## Problem

Given a string `s`, reverse only all the vowels in the string and return it.

The vowels are:

```text
a, e, i, o, u
A, E, I, O, U
```

**LeetCode Link:** https://leetcode.com/problems/reverse-vowels-of-a-string/

---

## Approach

Use the Two Pointers technique.

- Place one pointer at the beginning (`left`).
- Place another pointer at the end (`right`).
- Move `left` until it points to a vowel.
- Move `right` until it points to a vowel.
- Swap the vowels.
- Continue until the pointers meet.

---

## Solution (Python)

```python
class Solution:
    def reverseVowels(self, s):
        vowels = set("aeiouAEIOU")

        s = list(s)

        left = 0
        right = len(s) - 1

        while left < right:
              if s[left] in vowels :
                  if s[right] in vowels:
                      s[left] , s[right] = s[right], s[left]
                      left += 1
                      right -= 1
                  else:
                      right -= 1
              else:
                  left += 1
        return "".join(s)
```

---

## Complexity Analysis

### Time Complexity

- O(n)

Each character is visited at most once.

### Space Complexity

- O(n)

Strings are immutable in Python, so we convert the string into a list.

---

## Example 1

### Input

```text
s = "hello"
```

### Output

```text
"holle"
```

---

## Concepts Used

- Two Pointers
- Strings
- In-Place Swapping
- Character Matching

---
