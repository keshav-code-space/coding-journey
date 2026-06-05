# 59. Spiral Matrix II

## Problem

**LeetCode Link:** https://leetcode.com/problems/spiral-matrix-ii/

---

## Approach

Use four boundaries:

- `rowstart`
- `rowend`
- `colstart`
- `colend`

Fill the matrix layer by layer:

1. Left → Right
2. Top → Bottom
3. Right → Left
4. Bottom → Top

After completing a side, update the corresponding boundary.

Continue until all numbers from `1` to `n²` are placed.

---

## Solution (Python)

```python
class Solution(object):
    def generateMatrix(self, n):
        input1 = 1
        count = 0
        ans=[]
        for i in range(n):
            temp=[]
            for j in range(n):
                temp.append("")
            ans.append(temp)
        rowstart = 0
        colstart = 0
        rowend = n-1
        colend = n-1

        while count < (n*n):
            for i in range(colstart,colend+1):
                ans[rowstart][i] = input1
                count +=1
                input1 +=1
            rowstart += 1

            for i in range(rowstart,rowend+1):
                ans[i][colend] = input1
                count +=1 
                input1 +=1
            colend -= 1

            for i in range(colend,colstart-1,-1):
                ans[rowend][i] = input1
                input1 +=1
                count +=1
            rowend -= 1

            for i in range(rowend,rowstart-1,-1):
                ans[i][colstart] = input1
                input1 +=1
                count +=1
            colstart += 1
        return ans
        
```

---

## Complexity Analysis

### Time Complexity

```text
O(n²)
```

Every cell is filled exactly once.

### Space Complexity

```text
O(n²)
```

The output matrix itself contains `n²` elements.

---

## Example

### Input

```text
n = 3
```

### Output

```text
[
 [1,2,3],
 [8,9,4],
 [7,6,5]
]
```

--- 

## Concepts Used

- Matrix
- Simulation
- Boundary Traversal
- Spiral Order

---

