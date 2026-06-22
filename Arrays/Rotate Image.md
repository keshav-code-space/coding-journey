# 48. Rotate Image

## Problem

You are given an `n x n` 2D matrix representing an image.

Rotate the image by **90 degrees clockwise**.

You must rotate the image **in-place**, meaning you cannot allocate another 2D matrix.

**LeetCode Link:** https://leetcode.com/problems/rotate-image/

---

## Approach

The rotation can be performed in two steps:

1. **Transpose the matrix**
   - Swap `matrix[i][j]` with `matrix[j][i]`.

2. **Reverse each row**
   - Reverse every row of the transposed matrix.

This achieves a 90° clockwise rotation in-place.

---

## Solution (Python)

```python
class Solution:
    def rotate(self, matrix):
        n = len(matrix)

        # Transpose
        for i in range(n):
            for j in range(i + 1, n):
                matrix[i][j], matrix[j][i] = matrix[j][i], matrix[i][j]

        # Reverse each row
        for row in matrix:
            row.reverse()
```

---

## Complexity Analysis

### Time Complexity

- O(n²)

Every element is visited during the transpose operation.

### Space Complexity

- O(1)

Rotation is performed in-place.

---

## Concepts Used

- Matrix Manipulation
- In-Place Algorithms
- Transpose Matrix
- Two Pointers

---

