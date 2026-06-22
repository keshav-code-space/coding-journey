# 242. Valid Anagram

## Problem

Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, and `false` otherwise.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word, using all the original letters exactly once.

**LeetCode Link:** https://leetcode.com/problems/valid-anagram/

---

## Approach 1: Hash Map Frequency Count

Count the frequency of each character in both strings.

If the frequency maps are equal, the strings are anagrams.

---

## Solution (Python)

```python
class Solution:
    def isAnagram(self, s, t):
        if len(s) != len(t):
            return False

        count = {}

        for ch in s:
            count[ch] = count.get(ch, 0) + 1

        for ch in t:
            if ch not in count:
                return False

            count[ch] -= 1

            if count[ch] < 0:
                return False

        return True
```

---

## Approach 2: Sorting

```python
class Solution:
    def isAnagram(self, s, t):
        return sorted(s) == sorted(t)
```

---

## Complexity Analysis

### Frequency Count

- Time Complexity: O(n)
- Space Complexity: O(1)

(At most 26 lowercase English letters)

### Sorting

- Time Complexity: O(n log n)
- Space Complexity: O(n)

---

## Example

### Input

```text
s = "anagram"
t = "nagaram"
```

### Output

```text
True
```

---

## Concepts Used

- Hash Map
- String Manipulation
- Frequency Counting

---

