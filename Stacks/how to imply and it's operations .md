# Stack Data Structure

## What is a Stack?

A Stack is a linear data structure that follows:

```text
LIFO (Last In First Out)
```

The last element inserted is the first element removed.

Example:

```text
Push 10
Push 20
Push 30

Stack:

Top
 ↓
30
20
10
```

Removing an element:

```text
Pop()

Top
 ↓
20
10
```

---

## Real-Life Examples

### Browser History

```text
Visited:
Google
YouTube
GitHub

Back Button:
GitHub → YouTube → Google
```

### Undo Operation

```text
Type A
Type B
Type C

Undo:
C → B → A
```

---

# Stack Implementation Using Class

```python
class Stack:
    def __init__(self):
        self.stack = []

    def push(self, value):
        self.stack.append(value)

    def pop(self):
        if not self.is_empty():
            return self.stack.pop()
        else:
            raise IndexError("pop from empty stack")

    def peek(self):
        if not self.is_empty():
            return self.stack[-1]
        return None

    def is_empty(self):
        return len(self.stack) == 0

    def size(self):
        return  len(self.stack)

    def print_stack(self):
        print(self.stack)
```

---

# Operations on Stack

## 1. Push

Adds an element to the top of the stack.

```python
stack.push(10)
stack.push(20)
stack.push(30)
```

Result:

```text
Top
 ↓
30
20
10
```

### Time Complexity

```text
O(1)
```

---

## 2. Pop

Removes and returns the top element.

```python
stack.pop()
```

Output:

```text
30
```

Stack:

```text
Top
 ↓
20
10
```

### Time Complexity

```text
O(1)
```

---

## 3. Peek / Top

Returns the top element without removing it.

```python
stack.peek()
```

Output:

```text
20
```

### Time Complexity

```text
O(1)
```

---

## 4. isEmpty

Checks whether the stack is empty.

```python
stack.isEmpty()
```

Output:

```text
False
```

### Time Complexity

```text
O(1)
```

---

