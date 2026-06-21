# 503. Next Greater Element II

## Problem

Given a circular integer array `nums` (the next element of the last element is the first element of the array), return the next greater number for every element.

The next greater number of a number `x` is the first greater number traversing in its order in the array, which means you could search circularly to find its next greater number.

If it doesn't exist, return `-1`.

**LeetCode Link:** https://leetcode.com/problems/next-greater-element-ii/

---

## Approach: Monotonic Stack

### Key Idea

For a normal Next Greater Element problem:

```text
Traverse once.
```

For a circular array:

```text
Traverse twice.
```

Why?

Because elements at the end may find their next greater element at the beginning.

We simulate circular traversal using:

```python
for i in range(2 * n):
```

and access elements using:

```python
nums[i % n]
```

---

## Solution (Python)

```python
class Solution:
    def nextGreaterElements(self, nums):

        n = len(nums)

        answer = [-1] * n

        stack = []

        for i in range(2 * n):

            while stack and nums[stack[-1]] < nums[i % n]:
                index = stack.pop()
                answer[index] = nums[i % n]

            if i < n:
                stack.append(i)

        return answer
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

Although we loop `2n` times:

- Each index is pushed once.
- Each index is popped once.

Therefore:

```text
O(n)
```

---

### Space Complexity

```text
O(n)
```

For stack and result array.

---

## Example 1

### Input

```text
nums = [1,2,1]
```

### Output

```text
[2,-1,2]
```

### Explanation

```text
1 → next greater is 2
2 → no greater element
1 → wrap around → next greater is 2
```

---

## Why Traverse Twice?

Consider:

```text
[5,1,2,3,4]
```

For:

```text
4
```

the next greater element is:

```text
5
```

which appears at the beginning.

A single traversal would miss it.

---

## Concepts Used

- Monotonic Stack
- Circular Array
- Next Greater Element

---
