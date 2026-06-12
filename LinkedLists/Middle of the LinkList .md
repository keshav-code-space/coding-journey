# 876. Middle of the Linked List

## Problem

**LeetCode Link:** https://leetcode.com/problems/middle-of-the-linked-list/

---

## Approach

We use the **Two Pointer (Slow and Fast Pointer)** technique.

- `slow` moves one step at a time.
- `fast` moves two steps at a time.

When `fast` reaches the end of the linked list, `slow` will be at the middle node.

If there are two middle nodes, the problem requires returning the **second middle node**.

---

