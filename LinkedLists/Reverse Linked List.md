# 206. Reverse Linked List

## Problem

**LeetCode Link:** https://leetcode.com/problems/reverse-linked-list/

---

## Approach

We reverse the linked list by changing the direction of each node's `next` pointer.

Maintain three pointers:

- `prev` → Points to the previous node.
- `curr` → Points to the current node being processed.
- `nextNode` → Stores the next node before breaking the link.

Steps:

1. Save the next node.
2. Reverse the current node's link.
3. Move `prev` and `curr` one step forward.
4. Continue until `curr` becomes `None`.
5. `prev` will be the new head of the reversed linked list.

---

## Solution (Python)
