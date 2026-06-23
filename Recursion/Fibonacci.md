# 509. Fibonacci Number

## Problem

The Fibonacci numbers are defined as:

```text
F(0) = 0
F(1) = 1
```

For `n > 1`:

```text
F(n) = F(n-1) + F(n-2)
```

Given `n`, return `F(n)`.

**LeetCode Link:** https://leetcode.com/problems/fibonacci-number/

---

## Approach 1: Recursion

Directly implement the recurrence relation.

### Solution

```python
class Solution:
    def fib(self, n):
        if n <= 1:
            return n

        return self.fib(n - 1) + self.fib(n - 2)
```

### Complexity

- Time: O(2ⁿ)
- Space: O(n)

---

## Approach 2: Space Optimized DP

Only keep the previous two Fibonacci numbers.

### Solution

```python
class Solution:
    def fib(self, n):
        if n <= 1:
            return n

        prev2 = 0
        prev1 = 1

        for i in range(2, n + 1):
            curr = prev1 + prev2
            prev2 = prev1
            prev1 = curr

        return prev1
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

### Space Complexity

```text
O(1)
```

---

## Example

### Input

```text
n = 4
```

### Output

```text
3
```

---

## Concepts Used

- Recursion
- Memoization
- Space Optimization

---
