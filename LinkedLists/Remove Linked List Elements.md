# 203. Remove Linked List Elements

## Problem

**LeetCode Link:** https://leetcode.com/problems/remove-linked-list-elements/

---

## Approach

We need to remove all nodes whose value equals `val`.

A common challenge occurs when the head node itself needs to be removed.

To handle this cleanly, we use a **dummy node** that points to the head of the linked list.

Steps:

1. Create a dummy node and connect it to the head.
2. Traverse the list using a pointer `curr`.
3. If `curr.next.val == val`, skip that node.
4. Otherwise, move `curr` forward.
5. Return `dummy.next` as the new head.

This approach handles deletions at the beginning, middle, and end uniformly.

---
