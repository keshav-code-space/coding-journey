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

## Solution (Python)

```python
class Solution:
    def removeElements(self, head, val):

        dummy = ListNode(0)
        dummy.next = head

        curr = dummy

        while curr.next:

            if curr.next.val == val:
                curr.next = curr.next.next
            else:
                curr = curr.next

        return dummy.next
```

---

## Complexity Analysis

### Time Complexity

- O(n)

Each node is visited at most once.

### Space Complexity

- O(1)

Only a few extra pointers are used.

---

## Example Walkthrough

### Example 1

```text
Input:
head = [1,2,6,3,4,5,6]
val = 6
```

Initial List:

```text
1 → 2 → 6 → 3 → 4 → 5 → 6
```

Remove first occurrence of 6:

```text
1 → 2 → 3 → 4 → 5 → 6
```

Remove second occurrence of 6:

```text
1 → 2 → 3 → 4 → 5
```

Output:

```text
[1,2,3,4,5]
```

---

## Concepts Used

- Linked List
- Dummy Node
- Pointer Manipulation
- Traversal
- Node Deletion

---
