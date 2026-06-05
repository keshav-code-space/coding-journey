# Linked List - Complete Guide

## What is a Linked List?

A Linked List is a linear data structure where elements are stored in nodes.

Each node contains:

1. Data
2. Reference (pointer) to the next node

Unlike arrays, linked list elements are not stored in contiguous memory locations.

---

## Structure of a Node

```text
+------+------+
| Data | Next |
+------+------+
```

Example:

```text
10 -> 20 -> 30 -> None
```

Visualization:

```text
+----+------+    +----+------+    +----+------+
| 10 |   o-----> | 20 |   o-----> | 30 | None |
+----+------+    +----+------+    +----+------+
```

---

# Creating a Node

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

Create Nodes:

```python
first = Node(10)
second = Node(20)
third = Node(30)

first.next = second
second.next = third
```

Linked List:

```text
10 -> 20 -> 30 -> None
```

---

# Creating a Linked List Class

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


class LinkedList:
    def __init__(self):
        self.head = None
```

---

# Traversing a Linked List

```python
def display(self):
    temp = self.head

    while temp:
        print(temp.data, end=" -> ")
        temp = temp.next

    print("None")
```

Example:

```text
10 -> 20 -> 30 -> None
```

---

# Insertion Operations

## 1. Insert at Beginning

### Before

```text
10 -> 20 -> 30
```

### After inserting 5

```text
5 -> 10 -> 20 -> 30
```

### Code

```python
def insert_beginning(self, data):
    new_node = Node(data)

    new_node.next = self.head

    self.head = new_node
```

### Complexity

```text
Time: O(1)
Space: O(1)
```

---

## 2. Insert at End

### Before

```text
10 -> 20 -> 30
```

### After inserting 40

```text
10 -> 20 -> 30 -> 40
```

### Code

```python
def insert_end(self, data):
    new_node = Node(data)

    if self.head is None:
        self.head = new_node
        return

    temp = self.head

    while temp.next:
        temp = temp.next

    temp.next = new_node
```

### Complexity

```text
Time: O(n)
Space: O(1)
```

---

## 3. Insert at Position

Insert 25 at index 2

```text
10 -> 20 -> 25 -> 30
```

### Code

```python
def insert_position(self, pos, data):
    new_node = Node(data)

    if pos == 0:
        new_node.next = self.head
        self.head = new_node
        return

    temp = self.head

    for _ in range(pos - 1):
        temp = temp.next

    new_node.next = temp.next
    temp.next = new_node
```

### Complexity

```text
Time: O(n)
Space: O(1)
```

---

# Deletion Operations

## 1. Delete First Node

### Before

```text
10 -> 20 -> 30
```

### After

```text
20 -> 30
```

### Code

```python
def delete_beginning(self):
    if self.head:
        self.head = self.head.next
```

### Complexity

```text
Time: O(1)
```

---

## 2. Delete Last Node

### Before

```text
10 -> 20 -> 30
```

### After

```text
10 -> 20
```

### Code

```python
def delete_end(self):

    if self.head is None:
        return

    if self.head.next is None:
        self.head = None
        return

    temp = self.head

    while temp.next.next:
        temp = temp.next

    temp.next = None
```

### Complexity

```text
Time: O(n)
```

---

## 3. Delete by Value

Delete 20

```text
10 -> 20 -> 30
```

After:

```text
10 -> 30
```

### Code

```python
def delete_value(self, value):

    if self.head is None:
        return

    if self.head.data == value:
        self.head = self.head.next
        return

    temp = self.head

    while temp.next and temp.next.data != value:
        temp = temp.next

    if temp.next:
        temp.next = temp.next.next
```

### Complexity

```text
Time: O(n)
```

---

# Searching

Find whether a value exists.

### Code

```python
def search(self, value):

    temp = self.head

    while temp:

        if temp.data == value:
            return True

        temp = temp.next

    return False
```

### Complexity

```text
Time: O(n)
```

---

# Length of Linked List

### Code

```python
def length(self):

    count = 0

    temp = self.head

    while temp:
        count += 1
        temp = temp.next

    return count
```

### Complexity

```text
Time: O(n)
```

---

# Reverse a Linked List

### Before

```text
10 -> 20 -> 30 -> None
```

### After

```text
30 -> 20 -> 10 -> None
```

### Code

```python
def reverse(self):

    prev = None
    curr = self.head

    while curr:

        nxt = curr.next

        curr.next = prev

        prev = curr

        curr = nxt

    self.head = prev
```

### Complexity

```text
Time: O(n)
Space: O(1)
```

---

# Printing a Linked List

Printing a linked list means visiting every node from the head until `None`.

### Code

```python
def print_list(self):

    temp = self.head

    while temp:
        print(temp.data, end=" -> ")
        temp = temp.next

    print("None")
```

---

## Example

### Linked List

```text
10 -> 20 -> 30 -> None
```

### Driver Code

```python
ll = LinkedList()

ll.head = Node(10)
ll.head.next = Node(20)
ll.head.next.next = Node(30)

ll.print_list()
```

### Output

```text
10 -> 20 -> 30 -> None
```

---

## How It Works

```text
head
 ↓
10 -> 20 -> 30 -> None
```

Step 1:

```text
temp = head
print(10)
```

Step 2:

```text
temp = temp.next
print(20)
```

Step 3:

```text
temp = temp.next
print(30)
```

Step 4:

```text
temp = None
Stop
```

---

## Complexity

### Time Complexity

```text
O(n)
```

Every node is visited exactly once.

### Space Complexity

```text
O(1)
```

Only one temporary pointer is used.

---

## Recursive Printing

```python
def print_recursive(self, node):

    if node is None:
        print("None")
        return

    print(node.data, end=" -> ")

    self.print_recursive(node.next)
```

### Example Output

```text
10 -> 20 -> 30 -> None
```

### Complexity

```text
Time: O(n)
Space: O(n)
```

(The recursion stack stores one call for each node.)

---

# Common Interview Problems

## Easy

- Reverse Linked List (206)
- Linked List Cycle (141)
- Middle of Linked List (876)
- Remove Duplicates from Sorted List (83)

## Medium

- Add Two Numbers (2)
- Remove Nth Node From End (19)
- Odd Even Linked List (328)
- Sort List (148)

## Hard

- Merge k Sorted Lists (23)
- Reverse Nodes in k Group (25)
- Copy List with Random Pointer (138)

---

# Complexity Summary

| Operation | Time |
|------------|--------|
| Access by Index | O(n) |
| Search | O(n) |
| Insert Beginning | O(1) |
| Insert End | O(n) |
| Delete Beginning | O(1) |
| Delete End | O(n) |
| Reverse | O(n) |

---

# Key Learning

Linked Lists trade fast random access for efficient insertions and deletions.

### Array

```text
Access: O(1)
Insert/Delete: O(n)
```

### Linked List

```text
Access: O(n)
Insert/Delete at Head: O(1)
```

Think of a Linked List as a chain where each node knows only the location of the next node.
