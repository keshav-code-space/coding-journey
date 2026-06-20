# 69. Sqrt(x)

## Problem

simple use of inbuilt function but try to do it using not the inbuilt function 🙂.

Given a non-negative integer `x`, return the square root of `x` rounded down to the nearest integer.

You must not use any built-in exponent function or operator.

**LeetCode Link:** https://leetcode.com/problems/sqrtx/

---

## Approach: Binary Search

### Key Observation

For a number `mid`:

```text
mid² = x  -> Found answer
mid² < x  -> Search right half
mid² > x  -> Search left half
```

Since square roots form a sorted search space:

```text
1 ... x
```

Binary Search can be used.

---

## Solution (Python)

```python
class Solution:
    def mySqrt(self, x):

        if x < 2:
            return x

        left = 1
        right = x

        while left <= right:

            mid = (left + right) // 2

            if mid * mid == x:
                return mid

            elif mid * mid < x:
                left = mid + 1

            else:
                right = mid - 1

        return right
```

---

## Complexity Analysis

### Time Complexity

```text
O(log x)
```

Binary Search halves the search space each iteration.

---

### Space Complexity

```text
O(1)
```

Only a few variables are used.

---

## Example 1

### Input

```text
x = 4
```

### Output

```text
2
```

---

## Concepts Used

- Binary Search
- Math
- Search Space Reduction

---
