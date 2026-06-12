# LinkList class with all the operations.

## Node class 
```python
  class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

## LinkList class
```python
  class LinkList:
    def __init__(self):
        self.head = None
    # display the list

    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")

    # insert at head

    def insert(self,data,index):
        if self.head == None:
            self.head = Node(data)
        if index == 0:
            newnode = Node(data)
            newnode.next = self.head
            self.head = newnode
        temp = self.head
        while index != 0 :
            temp = temp.next
            index -= 1
        if temp == None:
            print(f"the index provided {index} is out of range.")
        temp.next = Node(data)
        return self.head
        
