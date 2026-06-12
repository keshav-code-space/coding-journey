# 237. Delete Node in a Linked List

## Problem

**LeetCode Link:** https://leetcode.com/problems/delete-node-in-a-linked-list/

---

## Approach

The given node is **not the tail node** and we do not have access to the head of the linked list.

Since we cannot access the previous node, we cannot remove the current node directly.

Instead:

1. Copy the value of the next node into the current node.
2. Skip the next node by updating the current node's `next` pointer.

This effectively removes the next node while making the current node appear deleted.

---
