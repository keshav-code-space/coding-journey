# 268. Missing Number

## Problem

Given an array nums containing n distinct numbers in the range:

[0, n]

return the only number in the range that is missing from the array.

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

## Solution (Python)

```python
class Solution:
    def missingNumber(self, nums):
        n = len(nums)
        expected_sum = n * (n + 1) // 2
        actual_sum = sum(nums)

        return expected_sum - actual_sum
```

---

## Complexity Analysis

### Time Complexity

- O(n)

We traverse the array once to calculate its sum.

### Space Complexity

- O(1)

Only a few extra variables are used.

---

## Concepts Used

- Array
- Mathematics
- Summation Formula
- Prefix Sum Concept

---
