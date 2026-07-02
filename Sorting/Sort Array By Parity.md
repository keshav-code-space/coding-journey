# 905. Sort Array By Parity

## Problem Statement

Given an integer array `nums`, move all the **even integers** to the beginning of the array, followed by all the **odd integers**.

Return **any array** that satisfies this condition.

> The relative order of even or odd numbers does **not** matter.

## Constraints

```text
1 <= nums.length <= 5000

0 <= nums[i] <= 5000
```

**LeetCode Link:** https://leetcode.com/problems/sort-array-by-parity/

---

# Approach 1: Two Pointers (Optimal)

## Key Idea

Use two pointers:

- `left` starts from the beginning.
- `right` starts from the end.

Move:

- `left` until it finds an **odd** number.
- `right` until it finds an **even** number.

Swap them.

Repeat until the pointers cross.

---

# Why Two Pointers?

We only need to separate:

```text
Even Numbers

Odd Numbers
```

We don't care about maintaining their relative order.

This makes the **Two Pointer** approach ideal.

---

# Solution

```python
class Solution:
    def sortArrayByParity(self, nums):

        left = 0
        right = len(nums) - 1

        while left < right:

            while left < right and nums[left] % 2 == 0:
                left += 1

            while left < right and nums[right] % 2 == 1:
                right -= 1

            nums[left], nums[right] = nums[right], nums[left]

        return nums
```

---

# Complexity Analysis

## Two Pointer

### Time Complexity

```text
O(n)
```

### Space Complexity

```text
O(1)
```

---

# Approach 2: Extra Array

## Key Idea

Create a new array.

- First add all even numbers.
- Then add all odd numbers.

---

## Solution

```python
class Solution:
    def sortArrayByParity(self, nums):

        ans = []

        for num in nums:
            if num % 2 == 0:
                ans.append(num)

        for num in nums:
            if num % 2 == 1:
                ans.append(num)

        return ans
```

---

# Complexity Analysis

## Extra Array

### Time Complexity

```text
O(n)
```

### Space Complexity

```text
O(n)
```

---

## Example 1

### Input

```text
nums = [3,1,2,4]
```

### Output

```text
[2,4,3,1]
```

Other valid outputs:

```text
[4,2,1,3]

[2,4,1,3]
```

---
