# 21. Merge Two Sorted Lists

## Problem

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists into one sorted linked list by splicing together the nodes of the first two lists.

Return the head of the merged linked list.

## Constraints

```text
The number of nodes in both lists is in the range [0, 50].

-100 <= Node.val <= 100

Both lists are sorted in non-decreasing order.
```

**LeetCode Link:** https://leetcode.com/problems/merge-two-sorted-lists/

---

## Approach

Since both linked lists are sorted, we can merge them by maintaining two pointers:

- `finalHead` → Points to the head of the merged list.
- `finalTail` → Points to the last node of the merged list.

Steps:

1. Compare the current nodes of both lists.
2. Select the smaller node.
3. If the merged list is empty, initialize both `finalHead` and `finalTail`.
4. Otherwise, attach the selected node after `finalTail` and move `finalTail` forward.
5. After one list is exhausted, attach the remaining nodes of the other list.

This allows us to merge the lists in-place without using any extra linked list.

---

## Solution (Python)

```python
class Solution:
    def mergeTwoLists(self, list1, list2):

        finalHead = None
        finalTail = None

        while list1 and list2:

            if list1.val <= list2.val:
                node = list1
                list1 = list1.next
            else:
                node = list2
                list2 = list2.next

            if finalHead is None:
                finalHead = node
                finalTail = node
            else:
                finalTail.next = node
                finalTail = node

        if list1:
            if finalHead is None:
                return list1
            finalTail.next = list1

        if list2:
            if finalHead is None:
                return list2
            finalTail.next = list2

        return finalHead
```

---

## Complexity Analysis

### Time Complexity

- O(n + m)

Where:

- `n` = length of `list1`
- `m` = length of `list2`

Each node is processed exactly once.

### Space Complexity

- O(1)

No extra linked list or data structure is used.

---

## Example Walkthrough

### Example 1

```text
Input:
list1 = [1,2,4]
list2 = [1,3,4]
```

Initial State:

```text
list1: 1 → 2 → 4
list2: 1 → 3 → 4

finalHead = None
finalTail = None
```

Step 1:

```text
Take 1 from list1

Merged:
1

finalHead = 1
finalTail = 1
```

Step 2:

```text
Take 1 from list2

Merged:
1 → 1

finalTail = second 1
```

Step 3:

```text
Take 2 from list1

Merged:
1 → 1 → 2
```

Step 4:

```text
Take 3 from list2

Merged:
1 → 1 → 2 → 3
```

Step 5:

```text
Take 4 from list1

Merged:
1 → 1 → 2 → 3 → 4
```

Attach Remaining Node:

```text
1 → 1 → 2 → 3 → 4 → 4
```

Output:

```text
[1,1,2,3,4,4]
```

---

## Concepts Used

- Linked List
- Two Pointers
- Head and Tail Construction
- In-Place Merging
- Sorted Lists

---
