# 54. Spiral Matrix

## Problem

**LeetCode Link:** https://leetcode.com/problems/spiral-matrix/

---

## Approach

Use four boundaries:

- `rowstart`
- `rowend`
- `colstart`
- `colend`

Traverse the matrix layer by layer:

1. Left → Right
2. Top → Bottom
3. Right → Left
4. Bottom → Top

After each traversal, update the corresponding boundary.

Continue until all elements have been visited.

---

## Solution (Python)

```python
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        m = len(matrix)
        n = len(matrix[0])
        count = 0
        ans=[]
        rowstart = 0
        colstart = 0
        rowend = m-1
        colend = n-1

        while count < (m*n):
            for i in range(colstart,colend+1):
                ans.append(matrix[rowstart][i])
                count +=1
            rowstart += 1
            if count == m*n:
                break

            for i in range(rowstart,rowend+1):
                ans.append(matrix[i][colend])
                count +=1 
            colend -= 1
            if count == m*n:
                break

            for i in range(colend,colstart-1,-1):
                ans.append(matrix[rowend][i])
                count +=1
            rowend -= 1
            if count == m*n:
                break

            for i in range(rowend,rowstart-1,-1):
                ans.append(matrix[i][colstart])
                count +=1
            colstart += 1
        return ans
```

---

## Complexity Analysis

### Time Complexity

- O(m × n)

Every element is visited exactly once.

### Space Complexity

- O(1)

Ignoring the output array.

---

## Example

### Input

```text
matrix =
[
 [1,2,3],
 [4,5,6],
 [7,8,9]
]
```

### Traversal

```text
1 → 2 → 3
          ↓
4       6 ↓
↑         ↓
7 ← 8 ← 9

Then visit 5
```

### Output

```text
[1,2,3,6,9,8,7,4,5]
```

---

## Concepts Used

- Matrix Traversal
- Four Pointers
- Boundary Management

---
