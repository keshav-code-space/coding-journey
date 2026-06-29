# 349. Intersection of Two Arrays

## Problem Statement

Given two integer arrays `nums1` and `nums2`, return an array of their **intersection**.

Each element in the result must be **unique**, and you may return the result in **any order**.

## Constraints

```text
1 <= nums1.length, nums2.length <= 1000

0 <= nums1[i], nums2[i] <= 1000
```

**LeetCode Link:** https://leetcode.com/problems/intersection-of-two-arrays/

---

# Approach 1: Using Hash Sets (Optimal)

## Key Idea

A set stores only **unique** elements.

Convert both arrays into sets and find their common elements.

---
