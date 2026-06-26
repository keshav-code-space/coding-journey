# 912. Sort an Array

## Problem Statement

Given an array of integers `nums`, sort the array in ascending order and return it.

You must solve the problem without using built-in sorting functions.

LeetCode : https://leetcode.com/problems/sort-an-array/description

---

## Solution

```python
class Solution:
    def sortArray(self, nums):

        def merge(left, right):

            result = []

            i = 0
            j = 0

            while i < len(left) and j < len(right):

                if left[i] <= right[j]:
                    result.append(left[i])
                    i += 1

                else:
                    result.append(right[j])
                    j += 1

            while i < len(left):
                result.append(left[i])
                i += 1

            while j < len(right):
                result.append(right[j])
                j += 1

            return result

        def mergeSort(arr):

            if len(arr) <= 1:
                return arr

            mid = len(arr) // 2

            left = mergeSort(arr[:mid])
            right = mergeSort(arr[mid:])

            return merge(left, right)

        return mergeSort(nums)
```

---

## Complexity Analysis

### Time Complexity

```text
O(n log n)
```

### Space Complexity

```text
O(n)
```

---


