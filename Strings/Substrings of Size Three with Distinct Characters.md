# 1876. Substrings of Size Three with Distinct Characters

## Problem

**LeetCode Link:** https://leetcode.com/problems/substrings-of-size-three-with-distinct-characters/

---

## Approach

Use a Sliding Window of size `3`.

For every substring of length `3`:

- Check if all three characters are distinct.
- If yes, increment the count.

Since the window size is fixed, checking distinct characters takes constant time.

---

## Solution (Python)

```python
class Solution:
    def countGoodSubstrings(self, s):

        count = 0

        for i in range(len(s) - 2):

            if len(set(s[i:i+3])) == 3:
                count += 1

        return count
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

We examine each window once.

Creating a set of 3 characters is:

```text
O(1)
```

Therefore:

```text
O(n)
```

---

### Space Complexity

```text
O(1)
```

The set can contain at most 3 characters.

---

## Example 1

### Input

```text
s = "xyzzaz"
```

### Windows

```text
xyz ✓
yzz ✗
zza ✗
zaz ✗
```

### Output

```text
1
```

---

## Alternative Solution

Without using a set:

```python
class Solution:
    def countGoodSubstrings(self, s):

        count = 0

        for i in range(len(s) - 2):

            a, b, c = s[i], s[i+1], s[i+2]

            if a != b and b != c and a != c:
                count += 1

        return count
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

## Concepts Used

- Sliding Window
- Strings
- Hash Set

---

