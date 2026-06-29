# 268. Missing Number

## Problem Statement

Given an array `nums` containing `n` distinct numbers in the range:

```text
[0, n]
```

return the only number in the range that is missing from the array.

**LeetCode Link:** https://leetcode.com/problems/missing-number/

---

# Approach 1: Sum Formula

## Key Idea

If no number were missing, the sum of numbers from:

```text
0 → n
```

would be:

```text
n × (n + 1) / 2
```

Subtract the actual sum of the array from the expected sum.

The difference is the missing number.

---

## Solution

```python
class Solution:
    def missingNumber(self, nums):

        n = len(nums)

        expected = n * (n + 1) // 2

        actual = sum(nums)

        return expected - actual
```

---
