# 1137. N-th Tribonacci Number

## Problem

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
