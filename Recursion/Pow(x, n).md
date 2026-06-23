# 50. Pow(x, n)

## Problem

Implement `pow(x, n)`, which calculates `x` raised to the power `n`.

```text
pow(x, n) = xⁿ
```

**LeetCode Link:** https://leetcode.com/problems/powx-n/

---

## Approach

Use Binary Exponentiation (Fast Power).

### Key Idea

Instead of multiplying `x` by itself `n` times:

```text
x × x × x × ... × x
```

use the fact that:

```text
xⁿ = (x²)^(n/2)      if n is even
xⁿ = x × xⁿ⁻¹        if n is odd
```

This reduces the exponent by half at each step.

---

---

## Recursive Solution

```python
class Solution:
    def myPow(self, x, n):

        def power(x, n):
            if n == 0:
                return 1

            half = power(x, n // 2)

            if n % 2 == 0:
                return half * half

            return x * half * half

        if n < 0:
            return 1 / power(x, -n)

        return power(x, n)
```

---

## Complexity Analysis

### Time Complexity

```text
O(log n)
```

At each step, `n` is divided by 2.

### Space Complexity

```text
O(log n)
```

Due to recursion stack.

---

## Example 1

### Input

```text
x = 2.00000
n = 10
```

### Output

```text
1024.00000
```

---

## Concepts Used

- Binary Exponentiation
- Divide and Conquer
- Recursion
- Math

---

