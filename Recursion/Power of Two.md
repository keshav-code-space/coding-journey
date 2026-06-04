# 231. Power of Two

## Problem

**LeetCode Link:** https://leetcode.com/problems/power-of-two/

---

## Approach : Repeated Division using Recursion

Keep dividing by 2 while the number is not 1 or 0.

```python
class Solution:
    def isPowerOfTwo(self, n):
        if n = 0:
            return False
        if n == 1:
            return True

        if n%2 != 0:
            return False

        return self.isPowerOfTwo(n//2)
```

---

## Complexity

### Time Complexity

```text
O(log n)
```

### Space Complexity

```text
O(log n)
```

---

## Concepts Used

- Recursion 
- Math

---
