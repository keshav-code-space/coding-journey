# 34. Find First and Last Position of Element in Sorted Array

## Problem

Given an array of integers nums sorted in non-decreasing order, find the starting and ending position of a given target value.

If the target is not found in the array, return:

[-1, -1]

You must write an algorithm with:

O(log n)

runtime complexity.

**LeetCode Link:** https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/

---

## Approach

Since the array is sorted, we can use **Binary Search**.

Perform two separate binary searches:

1. We are using LowerBound() for find the first index or the index from which the element starts.
2. We are using UpperBound() for find the last index or the index at which the element ends.

This ensures the required **O(log n)** time complexity.

---

## Solution (Python)

```python
class Solution:
    def lowerbound(self,nums,target):
        n=len(nums)
        start=0
        end=n-1
        ans=n
        while start<=end:
            mid = (start+end)//2
            if nums[mid] >= target:
                ans = mid
                end=mid-1
            else:
                start=mid + 1
        return ans
    def upperbound(self,nums,target):
        n=len(nums)
        start=0
        end=n-1
        ans=n
        while start<=end:
            mid = (start+end)//2
            if nums[mid] > target:
                ans = mid
                end= mid -1
            else:
                start= mid +1
        return ans
    def searchRange(self, nums, target):
        first_index=self.lowerbound(nums,target)
        last_index=self.upperbound(nums,target)

        if first_index == last_index:
            return [-1,-1]
        return [first_index,last_index-1]
```

---

## Complexity Analysis

### Time Complexity

- O(log n)

Two binary searches are performed.

### Space Complexity

- O(1)

Only a few extra variables are used.

---

## Concepts Used

- Binary Search
- Sorted Arrays
- Search Boundaries

---

