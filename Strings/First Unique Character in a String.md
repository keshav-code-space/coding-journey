# 387. First Unique Character in a String

## Problem

Given a string `s`, find the first non-repeating character in it and return its index.

If it does not exist, return `-1`.

**LeetCode Link:** https://leetcode.com/problems/first-unique-character-in-a-string/

---

## Approach: Hash Map Frequency Count

### Idea

1. Count the frequency of every character.
2. Traverse the string again.
3. Return the first index whose frequency is `1`.

---

## Solution (Python)

```python
class Solution:
    def firstUniqChar(self, s):

        freq = {}

        for ch in s:
            freq[ch] = freq.get(ch, 0) + 1

        for i in range(len(s)):

            if freq[s[i]] == 1:
                return i

        return -1
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

- First pass → count frequencies
- Second pass → find first unique character

Total:

```text
O(n)
```

---

### Space Complexity

```text
O(1)
```

At most 26 lowercase English letters are stored.

(Technically O(26) = O(1))

---

## Alternative Approach

Using `collections.Counter`.

```python
from collections import Counter

class Solution:
    def firstUniqChar(self, s):

        count = Counter(s)

        for i, ch in enumerate(s):

            if count[ch] == 1:
                return i

        return -1
```

---

## Complexity

### Time Complexity

```text
O(n)
```

### Space Complexity

```text
O(1)
```

---


## Example 1

### Input

```text
s = "leetcode"
```

### Output

```text
0
```

---

## Concepts Used

- Hash Map
- Frequency Counting
- Strings

---
