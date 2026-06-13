# 234. Palindrome Linked List

## Problem

**LeetCode Link:** https://leetcode.com/problems/palindrome-linked-list/

---

## Approach

To determine whether a linked list is a palindrome, we can:

1. Find the middle of the linked list using the Slow and Fast Pointer technique.
2. Reverse the second half of the linked list.
3. Compare the first half and the reversed second half node by node.
4. If all corresponding values match, the linked list is a palindrome.

This approach avoids using extra space and works in linear time.

---

## Solution (Python)

```python
class Solution:
    def isPalindrome(self, head):

        if head is None or head.next is None:
            return True

        slow = head
        fast = head

        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

        prev = None
        curr = slow

        while curr:
            nextNode = curr.next
            curr.next = prev
            prev = curr
            curr = nextNode

        left = head
        right = prev

        while right:
            if left.val != right.val:
                return False

            left = left.next
            right = right.next

        return True
```

---

## Complexity Analysis

### Time Complexity

- O(n)

One pass to find the middle, one pass to reverse, and one pass to compare.

### Space Complexity

- O(1)

The linked list is modified in-place without using extra data structures.

---

## Example Walkthrough

### Example 1

```text
Input:
1 → 2 → 2 → 1
```

Find Middle:

```text
slow = 2 (third node)
```

Reverse Second Half:

```text
2 → 1

becomes

1 → 2
```

Compare:

```text
1 == 1 ✓
2 == 2 ✓
```

Output:

```text
True
```

---

### Example 2

```text
Input:
1 → 2
```

Find Middle:

```text
slow = 2
```

Reverse Second Half:

```text
2
```

Compare:

```text
1 != 2 ✗
```

Output:

```text
False
```

---

## Concepts Used

- Linked List
- Slow and Fast Pointers
- Reverse Linked List
- Two Pointers
- In-Place Modification

---
