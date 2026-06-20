# 237. Delete Node in a Linked List

## Problem

use basice of linklist.

There is a singly-linked list `head` and you are given the node to be deleted `node`.

You are **not given access to the head of the list**. Instead, you are given direct access to the node that should be deleted.

Delete the given node. Note that by deleting the node, we do not mean removing it from memory. We mean:

- The value of the given node should not exist in the linked list.
- The number of nodes in the linked list should decrease by one.
- All values before the given node should remain in the same order.
- All values after the given node should remain in the same order.

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

## Solution (Python)

```python
class Solution:
    def deleteNode(self, node):
        node.val = node.next.val
        node.next = node.next.next
```

---

## Complexity Analysis

### Time Complexity

- O(1)

Only a constant number of operations are performed.

### Space Complexity

- O(1)

No extra space is used.

---

## Example Walkthrough

### Example 1

```text
Input: head = [4,5,1,9], node = 5
```

Initial Linked List:

```text
4 → 5 → 1 → 9
```

Copy the next node's value:

```text
4 → 1 → 1 → 9
```

Skip the next node:

```text
4 → 1 → 9
```

Output:

```text
[4,1,9]
```

---

## Concepts Used

- Linked List
- Pointer Manipulation
- In-Place Modification

---
