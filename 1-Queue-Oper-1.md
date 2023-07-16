# Queue Operations
## Enqueue
Enqueue operation is used to add an element to the queue. It follows the FIFO (First-In-First-Out) principle, where the element added first will be the first one to be dequeued. Here's a simple definition of the enqueue operation using easy-to-understand language:

To enqueue an element into a queue:

1. Create a new node or allocate memory for a new element.
2. Assign the value of the element to the node or element.
3. If the queue is empty, set the new node or element as both the front and rear of the queue.
4. If the queue is not empty, set the next pointer of the current rear element to the new node or element.
5. Set the new node or element as the new rear of the queue.

In simpler terms, to enqueue an element, you create a new element or node, set its value, and then add it to the end of the queue. If the queue is empty, the new element becomes both the front and rear of the queue. If the queue is not empty, the new element is linked to the previous rear element, and it becomes the new rear of the queue.

This process ensures that elements are added to the back of the queue and maintain their order, allowing for the FIFO behavior when dequeuing elements.

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

    def enqueue(self, data):
        new_node = Node(data)
        
        if self.rear is None:  # If the queue is empty
            self.front = new_node
            self.rear = new_node
        else:
            self.rear.next = new_node
            self.rear = new_node

    def display(self):
        current = self.front
        elements = []
        while current:
            elements.append(current.data)
            current = current.next
        print("Queue:", elements)
````
In this example, we create a Node class to represent each element in the queue. The Queue class has a front and rear attribute to keep track of the first and last elements in the queue, respectively. The enqueue method adds elements to the queue by creating a new node, linking it to the previous rear element, and updating the rear pointer. Finally, the display method is used to print the elements in the queue.

We can test this using:
````python
# Create an instance of the Queue
queue = Queue()

# Enqueue elements into the queue
queue.enqueue(10)
queue.enqueue(20)
queue.enqueue(30)
queue.enqueue(40)

# Display the queue
queue.display() #Queue: [10, 20, 30, 40]
````
[GO BACK - QUEUE Main](1-Queue.md)

[NEXT - QUEUE - Dequeue](1-Queue-Oper-2.md)