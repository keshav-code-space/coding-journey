# 82. Remove Duplicates from Sorted List II

## Problem

**LeetCode Link:** https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/

---

## Approach

Use a Dummy Node.

Maintain:

```text
prev → last confirmed unique node
curr → current node
```

If duplicates are found:

- Skip every node with that value.
- Connect `prev.next` to the first different node.

Otherwise:

- Move `prev` forward.

---

## Solution (Python)

```python
class Solution:
    def deleteDuplicates(self, head):

        dummy = ListNode(0)
        dummy.next = head

        prev = dummy
        curr = head

        while curr:

            if curr.next and curr.val == curr.next.val:

                duplicate = curr.val

                while curr and curr.val == duplicate:
                    curr = curr.next

                prev.next = curr

            else:
                prev = curr
                curr = curr.next

        return dummy.next
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

Only pointers are used.

---

## Example 1

### Input

```text
head = [1,2,3,3,4,4,5]
```

### Output

```text
[1,2,5]
```

### Explanation

```text
3 appears twice → remove all 3s
4 appears twice → remove all 4s
```

Remaining:

```text
1 -> 2 -> 5
```

---

## Why Use a Dummy Node?

Consider:

```text
1 -> 1 -> 2
```

The head itself is duplicated.

Without a dummy node:

```text
head must change
```

Using:

```python
dummy.next = head
```

allows us to remove the head using the same logic.

---

## Concepts Used

- Linked List
- Dummy Node
- Two Pointers
- Duplicate Removal

---
