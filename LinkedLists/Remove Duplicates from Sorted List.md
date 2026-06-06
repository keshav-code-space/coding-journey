# 83. Remove Duplicates from Sorted List

## Problem

**LeetCode Link:** https://leetcode.com/problems/remove-duplicates-from-sorted-list/

---

## Approach

Since the list is already sorted:

```text
Duplicate values will always be adjacent.
```

Traverse the list and compare the current node with the next node.

- If values are equal:
  - Skip the duplicate node.
- Otherwise:
  - Move forward.

---

## Solution (Python)

```python
class Solution:
    def deleteDuplicates(self, head):

        curr = head

        while curr and curr.next:

            if curr.val == curr.next.val:
                curr.next = curr.next.next

            else:
                curr = curr.next

        return head
```

---

## Complexity Analysis

### Time Complexity

```text
O(n)
```

Each node is visited at most once.

---

### Space Complexity

```text
O(1)
```

No extra data structures are used.

---

## Example 1

### Input

```text
head = [1,1,2]
```

### Output

```text
[1,2]
```

---

## Concepts Used

- Linked List
- Traversal
- In-Place Modification

---
