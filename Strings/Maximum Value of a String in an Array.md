# 2496. Maximum Value of a String in an Array

## Problem

**LeetCode Link:** https://leetcode.com/problems/maximum-value-of-a-string-in-an-array/

---

## Example 1

### Input

```text
strs = ["alic3","bob","3","4","00000"]
```

### Values

```text
"alic3" → length = 5
"bob"   → length = 3
"3"     → integer = 3
"4"     → integer = 4
"00000" → integer = 0
```

### Output

```text
5
```

---

## Approach

For each string:

- If every character is a digit:
  - Convert it to an integer.
- Otherwise:
  - Take its length.

Keep track of the maximum value.

---

## Solution (Python)

```python
class Solution:
    def maximumValue(self, strs):

        ans = 0

        for s in strs:

            if s.isdigit():
                ans = max(ans, int(s))
            else:
                ans = max(ans, len(s))

        return ans
```

---

## Complexity Analysis

### Time Complexity

```text
O(n × m)
```

Where:

- n = number of strings
- m = average string length

Each character may be checked once by `isdigit()`.

---

### Space Complexity

```text
O(1)
```

Only a few variables are used.

---

## Alternative Approach

Without using `isdigit()`:

```python
class Solution:
    def maximumValue(self, strs):

        ans = 0

        for s in strs:

            numeric = True

            for ch in s:

                if not ('0' <= ch <= '9'):
                    numeric = False
                    break

            if numeric:
                ans = max(ans, int(s))
            else:
                ans = max(ans, len(s))

        return ans
```

---

## Concepts Used

- Strings
- Character Checking
- Simulation

---
