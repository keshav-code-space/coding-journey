# Queue Data Structure

## What is Queue ? 

A Queue is linear data sturcture that follows:
```text
FIFO (First In First Out)
```

The first element inserted is the first element removed.

Example:

```text
Front                    Rear
 ↓                         ↓
10  →  20  →  30  →  40
```

Removing an element:

```text
Dequeue()

Front               Rear
 ↓                    ↓
20  →  30  →  40
```

---

## Real-Life Examples

### Ticket Counter

```text
Person A arrives
Person B arrives
Person C arrives
```

Service Order:

```text
A → B → C
```

---

### Printer Queue

```text
Print Job 1
Print Job 2
Print Job 3
```

Printing Order:

```text
Job 1 → Job 2 → Job 3
```

---

# Queue Implementation Using Class

```python
class Queue:

    def __init__(self):
        self.items = []

    def enqueue(self, data):
        self.items.append(data)

    def dequeue(self):

        if self.isEmpty():
            return "Queue Underflow"

        return self.items.pop(0)
    def front(self):

        if self.isEmpty():
            return None

        return self.items[0]

    def rear(self):

        if self.isEmpty():
            return None

        return self.items[-1]

    def isEmpty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

    def printQueue(self):
        print(self.items)
```

---

# Operations on Queue

## 1. Enqueue

Adds an element at the rear of the queue.

```python
queue.enqueue(10)
queue.enqueue(20)
queue.enqueue(30)
```

Result:

```text
Front          Rear
 ↓               ↓
10 → 20 → 30
```

### Time Complexity

```text
O(1)
```

---

## 2. Dequeue

Removes and returns the front element.

```python
queue.dequeue()
```

Output:

```text
10
```

Queue:

```text
Front     Rear
 ↓          ↓
20 → 30
```

### Time Complexity

```text
O(n)
```

Because elements shift left after `pop(0)`.

---
