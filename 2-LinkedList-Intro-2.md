# Introduction to Linked Lists
## Singly Linked List vs. Doubly Linked List :
In Python, linked lists can be implemented as either singly linked lists or doubly linked lists. These two variations differ in how nodes are structured and the operations they support. In this tutorial, we will explore the concepts of singly linked lists and doubly linked lists, along with easy-to-understand examples.

### Singly Linked List
In a singly linked list, each node contains data and a reference (or pointer) to the next node in the sequence. The last node points to None, indicating the end of the list. Singly linked lists allow traversal in only one direction, from the head (first node) to the tail (last node).

#### Implementation
Let's create a simple implementation of a singly linked list in Python:

````python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None
````
Here, we have a *Node class* representing a single node in the singly linked list, and a *SinglyLinkedList class* representing the entire list with a reference to the head node.

#### Example Usage
Let's create a singly linked list with some elements and visualize its structure:
````python
# Creating a singly linked list
linked_list = SinglyLinkedList()
linked_list.head = Node(1)
second_node = Node(2)
third_node = Node(3)

# Linking the nodes
linked_list.head.next = second_node
second_node.next = third_node
````
In the example above, code creates a singly linked list with three nodes, where the head node contains 1, the second node contains 2, and the third node contains 3. The next references are set to link the nodes together.

````rust
Singly Linked List:     1 -> 2 -> 3 -> None
````

### Doubly Linked List
In a doubly linked list, each node contains data and references (or pointers) to both the previous and next nodes in the sequence. This bidirectional linking allows traversal in both forward and backward directions.

#### Implementation
Let's create a simple implementation of a doubly linked list in Python:

````python
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None
````
Here, the Node class represents a single node in the doubly linked list, and the DoublyLinkedList class represents the entire list with a reference to the head node.

#### Example
Let's create a doubly linked list with some elements and visualize its structure:

````python
# Creating a doubly linked list
linked_list = DoublyLinkedList()
linked_list.head = Node(1)
second_node = Node(2)
third_node = Node(3)

# Linking the nodes
linked_list.head.next = second_node
second_node.prev = linked_list.head
second_node.next = third_node
third_node.prev = second_node
````
The above code creates a doubly linked list with three nodes, where the head node contains 1, the second node contains 2, and the third node contains 3. The prev and next references are set to link the nodes bidirectionally.
````rust
Doubly Linked List:     1 <-> 2 <-> 3 <-> None
````

[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Node Class](2-LinkedList-Imp-1.md)