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

## Solution (Python)

```python
class Solution:
    def middleNode(self, head):
        slow = head
        fast = head

        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

        return slow
```

---

## Complexity Analysis

### Time Complexity

- O(n)

The linked list is traversed only once.

### Space Complexity

- O(1)

Only two pointers are used.

---

## Example Walkthrough

### Example 1

```text
Input: head = [1,2,3,4,5]
```

Linked List:

```text
1 → 2 → 3 → 4 → 5
S
F
```

Iteration 1:

```text
1 → 2 → 3 → 4 → 5
    S
        F
```

Iteration 2:

```text
1 → 2 → 3 → 4 → 5
        S
                F
```

`fast` reaches the end, so `slow` is at:

```text
3
```

Output:

```text
[3,4,5]
```

---

## Concepts Used

- Linked List
- Two Pointers
- Slow and Fast Pointer Technique
- Traversal

---.
