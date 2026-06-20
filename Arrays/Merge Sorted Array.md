# 88. Merge Sorted Array

## Problem

You are given two integer arrays:

- `nums1` of length `m + n`
- `nums2` of length `n`

where:

- The first `m` elements of `nums1` are sorted.
- `nums2` contains `n` sorted elements.

Merge `nums2` into `nums1` as one sorted array.

**LeetCode Link:** https://leetcode.com/problems/merge-sorted-array/

---

## Approach: Three Pointers (Optimal)

### Key Idea

Instead of shifting elements in `nums1`, start filling from the end.

Use three pointers:

```text
i = m - 1     (last valid element in nums1)
j = n - 1     (last element in nums2)
k = m + n - 1 (last position in nums1)
```

Compare the larger element and place it at position `k`.

---

## Solution (Python)

```python
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        i=m-1
        j=n-1
        k=(n+m)-1

        while j>=0:
            if i<0 or nums2[j] > nums1[i]:
                nums1[k] = nums2[j]
                j-=1
                k-=1
            else:
                nums1[k] = nums1[i]
                i-=1
                k-=1
```

---

## Complexity Analysis

### Time Complexity

```text
O(m + n)
```

Each element is processed once.

### Space Complexity

```text
O(1)
```

Merge is done in-place.

---

## Example 1

### Input

```text
nums1 = [1,2,3,0,0,0]
m = 3

nums2 = [2,5,6]
n = 3
```

### Output

```text
[1,2,2,3,5,6]
```

---

## Concepts Used

- Two Pointers
- Three Pointers
- Arrays
- In-Place Merge

---
