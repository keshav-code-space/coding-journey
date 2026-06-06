# 19. Remove Nth Node From End of List

## Problem

**LeetCode Link:** https://leetcode.com/problems/remove-nth-node-from-end-of-list/

---

## Approach: Two Pointers (Fast & Slow)

### Key Idea

Maintain a gap of `n` nodes between two pointers.

1. Move `fast` pointer `n` steps ahead.
2. Move both `fast` and `slow` together.
3. When `fast` reaches the end:
   - `slow` will be just before the node to delete.
4. Remove the target node.

Use a dummy node to handle edge cases easily.

---

## Solution (Python)

```python
class Solution:
    def removeNthFromEnd(self, head, n):

        dummy = ListNode(0)
        dummy.next = head

        fast = dummy
        slow = dummy

        for _ in range(n):
            fast = fast.next

        while fast.next:
            fast = fast.next
            slow = slow.next

        slow.next = slow.next.next

        return dummy.next
```

---

## Complexity Analysis

### Time Complexity

```text
O(L)
```

Where `L` is the length of the linked list.

The list is traversed only once.

---

### Space Complexity

```text
O(1)
```

Only pointers are used.

---

## Why Use a Dummy Node?

Consider:

```text
head = [1]
n = 1
```

Removing the first node would require special handling.

Using:

```python
dummy.next = head
```

allows us to delete any node, including the head, with the same logic.

---

## Concepts Used

- Linked List
- Two Pointers
- Fast & Slow Pointer
- Dummy Node

---

