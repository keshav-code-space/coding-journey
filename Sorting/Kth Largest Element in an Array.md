# 215. Kth Largest Element in an Array

## Problem Statement

Given an integer array `nums` and an integer `k`, return the **kth largest element** in the array.

Note that it is the **kth largest element in the sorted order**, **not** the kth distinct element.

You must solve the problem without sorting the entire array if possible.

**LeetCode Link:** https://leetcode.com/problems/kth-largest-element-in-an-array/

---

# Approach 1: Sorting

## Idea

Sort the array in ascending order.

The kth largest element will be at index:

```text
len(nums) - k
```

---

## Solution

```python
class Solution:
    def findKthLargest(self, nums, k):

        nums.sort()

        return nums[len(nums) - k]
```

---

## Complexity Analysis

### Time Complexity

```text
O(n log n)
```

### Space Complexity

```text
O(1)
```

(Python's built-in sort uses extra space internally, but it is generally considered in-place.)

---
