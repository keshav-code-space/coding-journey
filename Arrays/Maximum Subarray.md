# 53. Maximum Subarray

## Problem

Given an integer array `nums`, find the contiguous subarray with the largest sum and return its sum.

A subarray is a contiguous non-empty sequence of elements within an array.


**LeetCode Link:** https://leetcode.com/problems/maximum-subarray/

---

## Approach

Use **Kadane's Algorithm**.

### Key Idea

At each position:

- Either extend the current subarray.
- Or start a new subarray from the current element.

Keep track of:

- `current_sum` → maximum subarray ending at the current index.
- `max_sum` → maximum subarray found so far.

---

## Solution (Python)

```python
class Solution:
    def maxSubArray(self, nums):
        current_sum = nums[0]
        max_sum = nums[0]

        for i in range(1, len(nums)):
            current_sum += nums[i]
            if current_sum > max_sum:
                max_sum = current_sum
            if current_sum <0:
                current_sum = 0

        return max_sum
```

---

## Complexity Analysis

### Time Complexity

- O(n)

We traverse the array only once.

### Space Complexity

- O(1)

Only a few variables are used.

---

## Example

### Input

```text
nums = [-2,1,-3,4,-1,2,1,-5,4]
```

### Kadane's Process

```text
current_sum = -2
max_sum = -2

1  → current_sum = 1
     max_sum = 1

-3 → current_sum = -2
     max_sum = 1

4  → current_sum = 4
     max_sum = 4

-1 → current_sum = 3
     max_sum = 4

2  → current_sum = 5
     max_sum = 5

1  → current_sum = 6
     max_sum = 6

-5 → current_sum = 1
     max_sum = 6

4  → current_sum = 5
     max_sum = 6
```

### Output

```text
6
```
---

## Concepts Used

- Arrays
- Dynamic Programming
- Kadane's Algorithm
- Greedy Optimization

---

### Pattern

- Dynamic Programming
- Kadane's Algorithm
- Maximum Subarray Problems
- Greedy + DP
