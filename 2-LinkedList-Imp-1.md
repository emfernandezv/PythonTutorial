# Implementing a Linked List
## Node Class

The first step in implementing a linked list is defining the Node class. Each node in the linked list will be an instance of this class and will contain the data and a reference to the next node.

````python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
````

In the __init__ method, we initialize the data attribute with the provided data value and set the next attribute to None.

[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Linked List Class](2-LinkedList-Imp-2.md)