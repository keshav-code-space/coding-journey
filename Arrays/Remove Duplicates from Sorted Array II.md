# 80. Remove Duplicates from Sorted Array II

## Problem 

Given an integer array `nums` sorted in non-decreasing order, remove some duplicates in-place such that each unique element appears at most twice.

The relative order of the elements should be kept the same.

Return `k` after placing the final result in the first `k` positions of `nums`.

**LeetCode Link:** https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/

---

## Approach

Use Two Pointers.

### Key Idea

Since the array is sorted:

- The first two occurrences of a number are always allowed.
- Starting from index `2`, compare the current element with the element two positions before the write pointer.
- If they are different, keep the element.

---

## Solution (Python)

```python
class Solution:
    def removeDuplicates(self, nums):

        if len(nums) <= 2:
            return len(nums)

        k = 2

        for i in range(2, len(nums)):

            if nums[i] != nums[k - 2]:
                nums[k] = nums[i]
                k += 1

        return k
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

The array is traversed once.

### Space Complexity

```text
O(1)
```

Modification is done in-place.

---

## Example 1

### Input

```text
nums = [1,1,1,2,2,3]
```

### Process

```text
Keep first two 1s

[1,1,_,_,_,_]

Third 1 is ignored

Keep 2

[1,1,2,_,_,_]

Keep second 2

[1,1,2,2,_,_]

Keep 3

[1,1,2,2,3,_]
```

### Output

```text
k = 5

nums = [1,1,2,2,3]
```

---

## Concepts Used

- Two Pointers
- Arrays
- In-Place Modification

---
