# 496. Next Greater Element I

## Problem

The next greater element of an element `x` in an array is the first greater element that appears to its right.

Given two arrays:

- `nums1` (subset of `nums2`)
- `nums2`

For each element in `nums1`, find its next greater element in `nums2`.

If it does not exist, return `-1`.

**LeetCode Link:** https://leetcode.com/problems/next-greater-element-i/


---

## Approach: Monotonic Stack

### Key Idea

Traverse `nums2` once.

Maintain a decreasing stack.

When a larger element appears:

```text
Current > Stack Top
```

we have found the next greater element for the stack top.

Store it in a hashmap.

---

## Solution (Python)

```python
class Solution:
    def nextGreaterElement(self, nums1, nums2):

        stack = []
        next_greater = {}

        for num in nums2:

            while stack and num > stack[-1]:
                next_greater[stack.pop()] = num

            stack.append(num)

        while stack:
            next_greater[stack.pop()] = -1

        return [next_greater[num] for num in nums1]
```

---

## Complexity Analysis

### Time Complexity

```text
O(n + m)
```

Where:

- n = len(nums1)
- m = len(nums2)

Each element is pushed and popped at most once.

---

### Space Complexity

```text
O(m)
```

For stack and hashmap.

---

## Example 1

### Input

```text
nums1 = [4,1,2]
nums2 = [1,3,4,2]
```

### Output

```text
[-1,3,-1]
```

### Explanation

```text
4 → no greater element → -1
1 → next greater is 3
2 → no greater element → -1
```

---

## Concepts Used

- Stack
- Monotonic Stack
- Hash Map
- Arrays

---
