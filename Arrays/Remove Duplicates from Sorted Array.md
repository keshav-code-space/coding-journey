# 26. Remove Duplicates from Sorted Array

## Problem
**LeetCode Link:** https://leetcode.com/problems/remove-duplicates-from-sorted-array/

---

## Approach

Use the Two Pointers technique.

- One pointer (`left`) keeps track of the position where the next unique element should be placed.
- Another pointer (`right`) traverses the array.
- Whenever a new unique element is found, place it at `left + 1` and move `left`.

---

## Solution (Python)

```python
class Solution:
    def removeDuplicates(self, nums):
        if not nums:
            return 0

        left = 0

        for right in range(1, len(nums)):
            if nums[right] != nums[left]:
                left += 1
                nums[left] = nums[right]

        return left + 1
```

---

## Complexity Analysis

### Time Complexity

- O(n)

Each element is visited once.

### Space Complexity

- O(1)

The modification is done in-place.

---

## Concepts Used

- Arrays
- Two Pointers
- In-Place Modification
