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

```python
class Solution:
    def reverseList(self, head):

        prev = None
        curr = head

        while curr:

            nextNode = curr.next

            curr.next = prev

            prev = curr
            curr = nextNode

        return prev
```

---

## Complexity Analysis

### Time Complexity

- O(n)

Each node is visited exactly once.

### Space Complexity

- O(1)

Only a few pointers are used.

---

## Example Walkthrough

### Example 1

```text
Input:
1 → 2 → 3 → 4 → 5
```

Initial State:

```text
prev = None
curr = 1
```

Step 1:

```text
nextNode = 2

1 → None

prev = 1
curr = 2
```

Current List:

```text
1 → None

2 → 3 → 4 → 5
```

---

Step 2:

```text
nextNode = 3

2 → 1 → None

prev = 2
curr = 3
```

Current List:

```text
2 → 1 → None

3 → 4 → 5
```

---

Step 3:

```text
nextNode = 4

3 → 2 → 1 → None

prev = 3
curr = 4
```

---

Step 4:

```text
nextNode = 5

4 → 3 → 2 → 1 → None

prev = 4
curr = 5
```

---

Step 5:

```text
nextNode = None

5 → 4 → 3 → 2 → 1 → None

prev = 5
curr = None
```

Loop ends.

Output:

```text
5 → 4 → 3 → 2 → 1
```

---

## Concepts Used

- Linked List
- Two Pointers
- Pointer Manipulation
- Iterative Traversal
- In-Place Reversal

---
