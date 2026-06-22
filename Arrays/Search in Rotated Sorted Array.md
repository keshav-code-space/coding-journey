# 33. Search in Rotated Sorted Array

## Problem

There is an integer array nums sorted in ascending order (with distinct values).

Before being passed to your function, the array is possibly rotated at an unknown pivot index.

For example:

[0,1,2,4,5,6,7]

might become:

[4,5,6,7,0,1,2]

Given the array nums after the possible rotation and an integer target, return the index of target if it exists in the array.

Otherwise, return:

-1

You must write an algorithm with:

O(log n)

runtime complexity.

**LeetCode Link:** https://leetcode.com/problems/search-in-rotated-sorted-array/

---

## Approach

Use a modified Binary Search.

At every step:

1. Find the middle element.
2. Determine which half is sorted.
3. Check if the target lies within the sorted half.
4. Discard the other half.

This maintains the O(log n) complexity of binary search.

---

## Solution (Python)

```python
class Solution:
    def search(self, nums, target):
        left = 0
        right = len(nums) - 1
        if nums[left] == target:
            return left
        elif nums[rigt] == target:
            return right

        while left <= right:
            mid = (left + right) // 2

            if nums[mid] == target:
                return mid

            # Left half is sorted
            if nums[left] <= nums[mid]:

                if nums[left] <= target < nums[mid]:
                    right = mid - 1
                else:
                    left = mid + 1

            # Right half is sorted
            else:

                if nums[mid] < target <= nums[right]:
                    left = mid + 1
                else:
                    right = mid - 1

        return -1
```

---

## Complexity Analysis

### Time Complexity

- O(log n)

Binary search halves the search space each iteration.

### Space Complexity

- O(1)

Only a few extra variables are used.

---

## Concepts Used

- Binary Search
- Rotated Sorted Array
- Divide and Conquer
- Search Space Reduction

---

