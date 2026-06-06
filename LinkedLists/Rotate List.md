# 61. Rotate List

## Problem

**LeetCode Link:** https://leetcode.com/problems/rotate-list/

---

## Approach

### Key Observation

Rotating by `k` positions is equivalent to:

```text
k = k % length
```

because after `length` rotations the list becomes the same.

---

### Steps

1. Find the length of the list.
2. Connect the tail to the head to form a circular list.
3. Compute the new tail position:

```text
length - k - 1
```

4. New head is:

```text
new_tail.next
```

5. Break the circle.

---

## Solution (Python)

```python
class Solution:
    def rotateRight(self, head, k):

        if not head or not head.next or k == 0:
            return head

        # Find length and tail
        length = 1
        tail = head

        while tail.next:
            tail = tail.next
            length += 1

        k = k % length

        if k == 0:
            return head

        # Make circular list
        tail.next = head

        # Find new tail
        steps = length - k - 1
        new_tail = head

        for _ in range(steps):
            new_tail = new_tail.next

        # New head
        new_head = new_tail.next

        # Break circle
        new_tail.next = None

        return new_head
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

- One traversal to find length.
- One traversal to find new tail.

---

### Space Complexity

```text
O(1)
```

No extra data structures are used.

---

## Concepts Used

- Linked List
- Circular Linked List
- Pointer Manipulation
- Modulo Arithmetic

---
