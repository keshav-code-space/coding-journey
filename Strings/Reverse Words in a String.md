# 151. Reverse Words in a String

## Problem

Given an input string `s`, reverse the order of the words.

A word is defined as a sequence of non-space characters.

The returned string should:

- Contain words in reverse order.
- Have only a single space between words.
- Have no leading or trailing spaces.

**LeetCode Link:** https://leetcode.com/problems/reverse-words-in-a-string/

---

## Approach 1: Using split()

### Idea

1. Split the string into words.
2. Reverse the list of words.
3. Join them back with a single space.

---

## Solution (Python)

```python
class Solution:
    def reverseWords(self, s):
        words = s.split()
        words.reverse()
        return " ".join(words)
```

---

## Complexity Analysis

### Time Complexity

- O(n)

Where `n` is the length of the string.

### Space Complexity

- O(n)

Extra space is used to store the words.

---

## Approach 2: Python One-Liner

```python
class Solution:
    def reverseWords(self, s):
        return " ".join(s.split()[::-1])
```

---

## Example 1

### Input

```text
s = "the sky is blue"
```

### Output

```text
"blue is sky the"
```

---

## Concepts Used

- Strings
- Arrays
- Reversal
- String Manipulation

---
