# 125. Valid Palindrome

## Problem

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward.

Given a string `s`, return `true` if it is a palindrome, or `false` otherwise.

**LeetCode Link:** https://leetcode.com/problems/valid-palindrome/

---

## Approach

Use the Two Pointers technique.

1. Place one pointer at the beginning.
2. Place another pointer at the end.
3. Skip non-alphanumeric characters.
4. Compare the characters after converting them to lowercase.
5. If they differ, return `False`.
6. Continue until the pointers cross.

---

## Solution (Python)

```python
class Solution:
    def isPalindrome(self, s):
        left = 0
        right = len(s) - 1

        while left < right:

            while left < right and not s[left].isalnum():
                left += 1

            while left < right and not s[right].isalnum():
                right -= 1

            if s[left].lower() != s[right].lower():
                return False

            left += 1
            right -= 1

        return True
```

---

## Complexity Analysis

### Time Complexity

- O(n)

Each character is visited at most once.

### Space Complexity

- O(1)

No extra data structures are used.

---

## Alternative Approach

Clean the string first and compare it with its reverse.

```python
class Solution:
    def isPalindrome(self, s):
        filtered = ""

        for ch in s:
            if ch.isalnum():
                filtered += ch.lower()

        return filtered == filtered[::-1]
```

### Complexity

- Time: O(n)
- Space: O(n)

---

## Example 1

### Input

```text
s = "A man, a plan, a canal: Panama"
```

### Output

```text
True
```

## Concepts Used

- Two Pointers
- Strings
- Character Processing

---
