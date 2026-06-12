# 21. Merge Two Sorted Lists

## Problem

**LeetCode Link:** https://leetcode.com/problems/merge-two-sorted-lists/

---

## Approach

Since both linked lists are sorted, we can merge them by maintaining two pointers:

- `finalHead` → Points to the head of the merged list.
- `finalTail` → Points to the last node of the merged list.

Steps:

1. Compare the current nodes of both lists.
2. Select the smaller node.
3. If the merged list is empty, initialize both `finalHead` and `finalTail`.
4. Otherwise, attach the selected node after `finalTail` and move `finalTail` forward.
5. After one list is exhausted, attach the remaining nodes of the other list.

This allows us to merge the lists in-place without using any extra linked list.

---

