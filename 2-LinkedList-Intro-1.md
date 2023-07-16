# Introduction to Linked Lists
## Definition
A Linked List is a linear data structure where elements are stored in nodes. Each node contains the data and a reference to the next node in the sequence. The last node points to None, indicating the end of the list. Unlike arrays, linked lists do not require contiguous memory allocation.

## Characteristics of a Linked List

* **Dynamic Size:** Linked lists have a dynamic size, meaning they can grow or shrink as elements are inserted or deleted. Unlike arrays with a fixed size, linked lists can accommodate a varying number of elements.

* **Node-based Structure:** Linked lists consist of nodes, where each node contains the actual data and a reference (or pointer) to the next node in the sequence. This node-based structure allows for efficient element insertion and deletion.

* **Memory Efficiency:** Linked lists are memory-efficient compared to arrays. They do not require contiguous memory allocation since each node can be located anywhere in the memory. This characteristic makes linked lists suitable for handling large or dynamically changing datasets.

* **Dynamic Insertion and Deletion:** Linked lists excel in supporting efficient insertion and deletion operations. Adding or removing elements in a linked list involves adjusting the pointers between nodes, rather than shifting elements as in an array. This property makes linked lists ideal for scenarios where frequent element modifications occur.

* **Flexible Traversal:** Linked lists allow for flexible traversal of elements. Starting from the head (the first node), you can navigate through the list by following the next pointers until you reach the desired node. This characteristic enables efficient searching, iterating, or accessing elements within the linked list.

* **Singly Linked or Doubly Linked:** Python linked lists can be implemented as either singly linked lists or doubly linked lists. Singly linked lists have nodes with a reference to the next node, allowing traversal in only one direction (forward). Doubly linked lists, on the other hand, have nodes with references to both the previous and next nodes, enabling traversal in both directions.

* **Variable Element Types:** Linked lists in Python can hold elements of various types. Each node can store any data type supported by Python, such as integers, strings, objects, or even other data structures. This flexibility allows linked lists to be used in diverse applications.

* **Tail Pointer Optimization:** In some linked list implementations, an additional pointer, called the "tail" pointer, is used to keep track of the last node. This optimization allows faster insertion at the end of the linked list, as it eliminates the need to traverse the entire list to find the last node.

[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Singly Linked vs Doubly Linked](2-LinkedList-Intro-2.md)