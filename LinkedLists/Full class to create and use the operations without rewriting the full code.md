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

    def insert_begin(self,data):
        if self.head == None:
            self.head = Node(data)
        newnode = Node(data)
        newnode.next = self.head
        self.head = newnode

    # insert at the end

    def insert_end(self,data):
        newnode = Node(data)

        if self.head is None:
            self.head = newnode

        temp = self.head
        while temp.next :
            temp =temp.next

        temp.next = newnode

    #insert at the position (0-length of the LinkList)

    def insert_position(self,data,index):

        if index == 0 :
              self.insert_begin(data)
              return

        newnode = Node(data)
        temp = self.head

        for i in range(index-1):
            if temp is None:
                return
            temp = temp.next

        if temp is None:
            return

        newnode.next = temp.next
        temp.next = newnode
    
    # delete from beginning.
    
    def delete_begin(self):
        if self.head:
            self.head = self.head.next
            
    # delete from end.
    
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

    #delete by value

    def delete_value(self, val):
        if self.head is None:
            return
        if self.head.data == val:
            self.head = self.head.next
            return 
    
        temp = self.head
        while temp.next is not None and temp.next.data != val:      
            temp = temp.next
        
        if temp.next:
            temp.next = temp.next.next
    
    # search element 
    
    def serch(self, val):
      temp =self.head
      postion = 0
      while temp is not None:
          if temp.data == val:
              return postion
          temp = temp.next
          postion += 1
  
    # length of linked list
    
    def length(self):
        temp = self.head
        count = 0
        while temp:
            count +=1 
            temp = temp.next
            
      return count

    
