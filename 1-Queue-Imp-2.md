# Implementing a Queue
## Linked list-based implementation.
A *linked list-based implementation* of a queue is a way to represent a queue data structure using a linked list in Python. In this implementation, the elements of the queue are stored as nodes in the linked list, and additional elements are added or removed by manipulating the pointers between the nodes.

Here's how the linked list-based implementation works:

* Each node in the linked list represents an element in the queue. It contains the actual data and a pointer to the next node in the list.
* The front of the queue is represented by a pointer to the first node in the linked list, and the rear of the queue is represented by a pointer to the last node.
* Initially, both the front and rear pointers are set to None to indicate an empty queue.
* When an element is enqueued (added) to the queue, a new node is created with the data and its next pointer is set to None. If the queue is empty, both the front and rear pointers are set to the new node. Otherwise, the next pointer of the current rear node is updated to point to the new node, and the rear pointer is updated to the new node.
* When an element is dequeued (removed) from the queue, the node pointed to by the front pointer is removed from the list. The front pointer is updated to point to the next node in the list.
* The linked list-based implementation allows dynamic resizing of the queue as it can grow or shrink based on the number of elements added or removed.
* The enqueue and dequeue operations in the linked list-based implementation have a time complexity of O(1) on average, making it efficient for adding and removing elements from the queue.

Overall, the linked list-based implementation provides a flexible and efficient way to implement a queue data structure using a linked list, making it suitable for scenarios where the size of the queue may change dynamically.

Here an example:

````python 
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Queue:
    def __init__(self):
        self.front = None
        self.rear = None

    def is_empty(self):
        return self.front is None

    def enqueue(self, data):
        new_node = Node(data)
        if self.is_empty():
            self.front = self.rear = new_node
        else:
            self.rear.next = new_node
            self.rear = new_node

    def dequeue(self):
        if self.is_empty():
            return None
        else:
            removed_node = self.front
            self.front = self.front.next
            if self.front is None:
                self.rear = None
            return removed_node.data
````
In the linked list-based implementation, we define a Node class to represent each element in the queue. The Queue class maintains the front and rear pointers and provides methods to enqueue and dequeue elements.

We can test this:

````python
# Test Case 1
queue = Queue()
queue.enqueue(10)
queue.enqueue(20)
queue.enqueue(30)
print(queue.dequeue())  # Output: 10
print(queue.dequeue())  # Output: 20

# Test Case 2
queue = Queue()
print(queue.dequeue())  # Output: None
queue.enqueue(10)
print(queue.dequeue())  # Output: 10
````

**Expected Results**

* **Test Case 1**: The elements 10 and 20 are enqueued into the queue, and then the first two elements are dequeued. The expected output is 10 followed by 20.
* **Test Case 2**: The queue is initially empty, so dequeuing an element should return None. Then, 10 is enqueued and dequeued, resulting in the expected output of 10.

[GO BACK - QUEUE Main](1-Queue.md)

[NEXT - QUEUE - Enqueue](1-Queue-Oper-1.md)