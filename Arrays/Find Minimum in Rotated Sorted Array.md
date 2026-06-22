# 153. Find Minimum in Rotated Sorted Array

## Problem

Suppose an array of length `n` sorted in ascending order is rotated between `1` and `n` times.

Find the minimum element.

You must write an algorithm that runs in:

```text
O(log n)
```

**LeetCode Link:** https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/

---

## Approach: Binary Search

### Key Observation

A rotated sorted array consists of:

```text
Sorted Part 1
Sorted Part 2
```

Example:

```text
[4,5,6,7,0,1,2]
```

The minimum element is where the rotation occurs.

Use Binary Search to determine which half contains the minimum.

---

## Solution (Python)

```python
class Solution:
    def findMin(self, nums):

        left = 0
        right = len(nums) - 1

        while left < right:

            mid = (left + right) // 2

            if nums[mid] > nums[right]:
                left = mid + 1

            else:
                right = mid

        return nums[left]
```

---

## Complexity Analysis

### Time Complexity

```text
O(log n)
```

Binary Search halves the search space each iteration.

### Space Complexity

```text
O(1)
```

Only a few variables are used.

---

## Example 1

### Input

```text
nums = [3,4,5,1,2]
```

### Output

```text
1
```

---

## Why Compare With nums[right]?

If:

```text
nums[mid] > nums[right]
```

then:

```text
mid is in the left sorted portion
```

and the minimum must be on the right.

---

If:

```text
nums[mid] <= nums[right]
```

then:

```text
mid may be the minimum
```

so keep it in the search space.

---

## Concepts Used

- Binary Search
- Rotated Sorted Array
- Search Space Reduction

---
