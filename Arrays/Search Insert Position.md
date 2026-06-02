# 35. Search Insert Position

## Problem

**LeetCode Link:** https://leetcode.com/problems/search-insert-position/

---

## Approach

Since the array is sorted, use **Binary Search**.

- If the target is found, return its index.
- If not found, the `left` pointer will indicate the correct insertion position after the search ends.
- For these type of problems we have a algo of LowerBound.
---

## Solution (Python)

```python
class Solution:
    def LowerBound(self,nums,target):
        left = 0
        right = len(nums) - 1
        ans = len(nums)

        while left <= right:
            mid = (left + right) // 2

            if nums[mid] >= target:
                ans = nums[mid]
                right = mid - 1
            else:
                left = mid + 1

        return ans
        
    def searchInsert(self, nums, target):
        retrurn self.LowerBound(nums,target)
```

---

## Complexity Analysis

### Time Complexity

- O(log n)

Binary Search reduces the search space by half in each iteration.

### Space Complexity

- O(1)

Some extra space is used.

---

## Concepts Used

- Binary Search
- Sorted Arrays
- Search Space Reduction

---
