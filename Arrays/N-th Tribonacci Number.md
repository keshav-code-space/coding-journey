# 1137. N-th Tribonacci Number

## Problem

The Tribonacci sequence Tn is defined as follows:

T0 = 0
T1 = 1
T2 = 1

and for:

n >= 0

the next number is the sum of the previous three numbers:

T(n+3) = T(n) + T(n+1) + T(n+2)

Given an integer n, return the value of:

Tn

**LeetCode Link:** https://leetcode.com/problems/n-th-tribonacci-number/

---

## Approach

The Tribonacci sequence is defined as:

- T₀ = 0
- T₁ = 1
- T₂ = 1

For n ≥ 3:

```
Tn = Tn-1 + Tn-2 + Tn-3
```

Instead of using recursion, we can iteratively compute the sequence while storing only the last three values.

At each step:

1. Calculate the next Tribonacci number.
2. Shift the previous three values forward.
3. Continue until we reach the nth term.

This gives an efficient solution with constant extra space.

---


## Solution (Python)

```python
class Solution:
    def tribonacci(self, n):
        if n == 0:
            return 0
        if n <= 2:
            return 1

        a, b, c = 0, 1, 1

        for _ in range(3, n + 1):
            a, b, c = b, c, a + b + c

        return c
```

---

## Complexity Analysis

### Time Complexity

- O(n)

We iterate from 3 to n once.

### Space Complexity

- O(1)

Only three variables are maintained regardless of input size.

---

## Example Walkthrough

### Example 1

```text
Input: n = 4
```

Initial values:

```text
T0 = 0
T1 = 1
T2 = 1
```

Calculate:

```text
T3 = T2 + T1 + T0
   = 1 + 1 + 0
   = 2

T4 = T3 + T2 + T1
   = 2 + 1 + 1
   = 4
```

Output:

```text
4
```

---

### Example 2

```text
Input: n = 5
```

Sequence:

```text
0, 1, 1, 2, 4, 7
```

Output:

```text
7
```

---

## Concepts Used

- Dynamic Programming
- Iteration
- Recurrence Relations
- Space Optimization

---
