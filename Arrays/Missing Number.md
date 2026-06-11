# 268. Missing Number

## Problem

**LeetCode Link:** https://leetcode.com/problems/missing-number/

---

## Approach

The array contains `n` distinct numbers from the range `[0, n]`, with exactly one number missing.

We can calculate:

1. The expected sum of all numbers from `0` to `n` using the formula:
   ```
   n * (n + 1) / 2
   ```
2. The actual sum of all elements in the array.
3. The difference between the expected sum and actual sum gives the missing number.

This provides an optimal solution with **O(n)** time complexity and **O(1)** extra space.

---



---
