# 74. Search a 2D Matrix

## Problem

tricky one this time.

You are given an `m x n` integer matrix with the following properties:

1. Each row is sorted in non-decreasing order.
2. The first integer of each row is greater than the last integer of the previous row.

Given an integer `target`, return `true` if `target` is in the matrix, or `false` otherwise.

**LeetCode Link:** https://leetcode.com/problems/search-a-2d-matrix/

---

## Approach

Treat the matrix as a single sorted array.

Example:

```text
[
 [1,3,5,7],
 [10,11,16,20],
 [23,30,34,60]
]
```

can be viewed as:

```text
[1,3,5,7,10,11,16,20,23,30,34,60]
```

Perform Binary Search on indices from:

```text
0 to (m × n - 1)
```

Convert a 1D index back into matrix coordinates:

```text
row = mid // cols
col = mid % cols
```

---

## Solution (Python)

```python
class Solution:
    def searchMatrix(self, matrix, target):

        rows = len(matrix)
        cols = len(matrix[0])

        left = 0
        right = rows * cols - 1

        while left <= right:

            mid = (left + right) // 2

            row = mid // cols
            col = mid % cols

            value = matrix[row][col]

            if value == target:
                return True

            elif value < target:
                left = mid + 1

            else:
                right = mid - 1

        return False
```

---

## Complexity Analysis

### Time Complexity

```text
O(log(m × n))
```

Binary search halves the search space each iteration.

### Space Complexity

```text
O(1)
```

Only a few variables are used.

---

## Example 1

### Input

```text
matrix =
[
 [1,3,5,7],
 [10,11,16,20],
 [23,30,34,60]
]

target = 3
```

### Output

```text
True
```

---

## Concepts Used

- Binary Search
- Matrix
- Index Mapping

---
