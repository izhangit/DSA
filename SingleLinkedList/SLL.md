# Data Structure and Algorithm

### A data structure is a storage that is used to store and organize data. It is a way of arranging data on a computer so that it can be accessed and updated efficiently.



## Linked List Data Structure

#### A linked list is a type of linear data structure similar to arrays. It is a collection of nodes that are linked with each other. A node contains two things first is data and second is a link that connects it with another node. Below is an example of a linked list with four nodes and each node contains character data and a link to another node. Our first node is where head points and we can access all the elements of the linked list using the head.

!![SLL.png](696f1100-922d-469f-8c8b-19b95172cc49.png)


# Single Linked List


```python
# Create a Node
class Node:
    def __init__(self,data):
        self.data = data
        self.next = None    # Address of the Next Node

# Define head is None
class SingleLinkedList:
    def __init__(self):
        self.head = None

# Insertion at the Begining
    def Insert_at_Begining(self,data):
        nb = Node(data)
        nb.next = self.head
        self.head = nb

# Insertion at the End
    def Insert_at_End(self,data):
        ne = Node(data)
        temp = self.head
        while temp.next != None:
            temp = temp.next
        temp.next = ne

# Insertion at Specific Position
    def Insert_at_Specific_Position(self,targetdata,data):
        np = Node(data)
        temp = self.head
        while temp.data != targetdata:
            temp = temp.next
        np.next = temp.next
        temp.next = np
        
# Deletion at the Begining
    def Deletion_at_Begining(self):
        self.head = self.head.next

# Deletion at the End
    def Deletion_at_End(self):
        temp = self.head
        while temp.next.next != None:
            temp = temp.next
        temp.next = None

# Deletion at the Specific Position
    def Deletion_at_Specific_Position(self,data):
        temp = self.head
        nd = Node(data)
        while temp.next.data != data:
            temp = temp.next
        temp.next = temp.next.next
    
# Display Linked List
    def display(self):
        if self.head is None:
            print("Linked List is Empty")
        else:
            temp = self.head
            while temp:
                print(temp.data,"-->",end = " ")
                temp = temp.next
```

## Function Call


```python
L = SingleLinkedList()
# Insertion part ............

n = Node(10)
L.head = n
n1 = Node(20)
L.head.next = n1

# Insertion at the Begining
L.Insert_at_Begining(5)
L.Insert_at_Begining(2)

# Insertion at the Ending
L.Insert_at_End(30)
L.Insert_at_End(40)
L.Insert_at_End(45)

# Insertion at Specific Position
L.Insert_at_Specific_Position(20,25)
L.Insert_at_Specific_Position(10,15)


# Deletion part ................

# Deletion at the Begining
L.Deletion_at_Begining()

# Deletion at the End
L.Deletion_at_End()

# Deletion at Specific Data Position
L.Deletion_at_Specific_Position(15)
L.Deletion_at_Specific_Position(25)


# Display 
L.display()
```

    5 --> 10 --> 20 --> 30 --> 40 --> 
