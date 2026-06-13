# 234. Palindrome Linked List

## Problem

**LeetCode Link:** https://leetcode.com/problems/palindrome-linked-list/

---

## Approach

To determine whether a linked list is a palindrome, we can:

1. Find the middle of the linked list using the Slow and Fast Pointer technique.
2. Reverse the second half of the linked list.
3. Compare the first half and the reversed second half node by node.
4. If all corresponding values match, the linked list is a palindrome.

This approach avoids using extra space and works in linear time.

---
