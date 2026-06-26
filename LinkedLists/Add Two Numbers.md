# 2. Add Two Numbers

## Problem

You are given two non-empty linked lists representing two non-negative integers.

The digits are stored in reverse order, and each node contains a single digit.

Add the two numbers and return the sum as a linked list.

**LeetCode Link:** https://leetcode.com/problems/add-two-numbers/

---

## Approach

Simulate elementary addition.

For each pair of nodes:

1. Add digits from both lists.
2. Add any carry from the previous step.
3. Store the digit `(sum % 10)`.
4. Update carry `(sum // 10)`.
5. Move both pointers forward.

Continue until:

- Both lists are exhausted.
- Carry becomes 0.

---

## Solution (Python)

```python
class Solution:
    def addTwoNumbers(self, l1, l2):

        dummy = ListNode(0)
        curr = dummy

        carry = 0

        while l1 or l2 or carry:

            val1 = l1.val if l1 else 0
            val2 = l2.val if l2 else 0

            total = val1 + val2 + carry

            carry = total // 10

            curr.next = ListNode(total % 10)

            curr = curr.next

            if l1:
                l1 = l1.next

            if l2:
                l2 = l2.next

        return dummy.next
```

---

## Complexity Analysis

### Time Complexity

```text
O(max(m, n))
```

Where:

- m = length of l1
- n = length of l2

We visit each node once.

---

### Space Complexity

```text
O(max(m, n))
```

A new linked list is created for the result.

---

## Concepts Used

- Linked List
- Simulation
- Carry Handling
- Dummy Node

---
