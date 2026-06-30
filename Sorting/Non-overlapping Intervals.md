# 435. Non-overlapping Intervals

## Problem Statement

Given an array of intervals where:

```text
intervals[i] = [starti, endi]
```

Return the **minimum number of intervals you need to remove** to make the rest of the intervals **non-overlapping**.

> Two intervals overlap if one interval starts before the previous interval ends.

## Constraints

```text
1 <= intervals.length <= 10^5

intervals[i].length == 2

-5 * 10^4 <= starti < endi <= 5 * 10^4
```

**LeetCode Link:** https://leetcode.com/problems/non-overlapping-intervals/ 

---

# Approach: Greedy

## Key Idea

To maximize the number of intervals we keep, we should always keep the interval that **ends earliest**.

Why?

An interval with a smaller ending time leaves more room for future intervals.

---
