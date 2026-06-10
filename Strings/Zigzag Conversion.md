# 6. Zigzag Conversion

## Problem

The string `"PAYPALISHIRING"` is written in a zigzag pattern on a given number of rows:

```text
P   A   H   N
A P L S I I G
Y   I   R
```

Read line by line:

```text
PAHNAPLSIIGYIR
```

Given a string `s` and an integer `numRows`, return the zigzag conversion.

**LeetCode Link:** https://leetcode.com/problems/zigzag-conversion/

---
## Approach

### Key Idea

Simulate writing characters row by row.

Move:

```text
Down
↓
```

until the last row.

Then move:

```text
Up
↑
```

until the first row.

Store characters for each row separately.

---

## Solution

```python
class Solution:
    def convert(self, s, numRows):

        if numRows == 1 or numRows >= len(s):
            return s

        rows = [""] * numRows

        curr_row = 0
        direction = 1

        for ch in s:

            rows[curr_row] += ch

            if curr_row == 0:
                direction = 1

            elif curr_row == numRows - 1:
                direction = -1

            curr_row += direction

        return "".join(rows)
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

Each character is visited once.

---

### Space Complexity

```text
O(n)
```

The rows collectively store all characters.

---

## Example 1

### Input

```text
s = "PAYPALISHIRING"
numRows = 3
```

### Output

```text
"PAHNAPLSIIGYIR"
```

---

## Concepts Used

- Strings
- Simulation
- Array/List
- Pattern Traversal

---
