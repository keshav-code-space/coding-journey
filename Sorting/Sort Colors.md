# 75. Sort Colors

## Problem

Given an array `nums` with `n` objects colored:

```text
0 -> Red
1 -> White
2 -> Blue
```

Sort them in-place so that objects of the same color are adjacent, with the colors in the order:

```text
0, 1, 2
```

You must solve this problem without using the library's sort function.

**LeetCode Link:** https://leetcode.com/problems/sort-colors/

---

## Approach: Dutch National Flag Algorithm

Use three pointers:

```text
low
mid
high
```

Maintain:

```text
[0 ... low-1]     -> 0s
[low ... mid-1]   -> 1s
[mid ... high]    -> Unknown
[high+1 ... end]  -> 2s
```

Process the array until `mid > high`.

---
