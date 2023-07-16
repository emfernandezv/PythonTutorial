# Queue Operations
## Dequeue
Dequeue operation in a queue data structure removes the element from the front of the queue. It follows the FIFO (First-In-First-Out) principle, meaning that the element that was added first will be the first one to be removed.

When we dequeue an element from a queue, the front pointer moves to the next element, effectively removing the element from the queue. This operation allows us to retrieve and remove elements from the queue in the order they were added.

If the queue is empty and there are no elements to dequeue, an error or exception may be raised, depending on the programming language or implementation.

The dequeue operation is commonly used when we want to process elements in the order they arrived, such as handling tasks in a queue or processing messages in a messaging system.

It's important to note that in some programming languages or implementations, the dequeue operation may be called differently, such as pop, shift, or dequeue_front, but the underlying concept remains the same.

Here is an example:
````python
class Queue:
    def __init__(self):
        self.queue = []

    def enqueue(self, item):
        self.queue.append(item)

    def dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)
        else:
            raise IndexError("Cannot dequeue from an empty queue")

    def is_empty(self):
        return len(self.queue) == 0
````
In this example, we define a Queue class that internally uses a list to store the elements. The enqueue method adds elements to the end of the list, and the dequeue method removes elements from the front of the list using the pop(0) function.

We enqueue three elements (10, 20, and 30) and then dequeue them one by one. Finally, we check if the queue is empty using the is_empty method. The example also demonstrates the case when we try to dequeue from an empty queue, which raises an IndexError indicating that the queue is empty.

We can test this using:
````python
# Creating a queue
queue = Queue()

# Enqueueing elements
queue.enqueue(10)
queue.enqueue(20)
queue.enqueue(30)

# Dequeueing elements
print(queue.dequeue())  # Output: 10
print(queue.dequeue())  # Output: 20

# Checking if the queue is empty
print(queue.is_empty())  # Output: False

# Dequeueing remaining elements
print(queue.dequeue())  # Output: 30

# Trying to dequeue from an empty queue
print(queue.dequeue())  # Output: IndexError: Cannot dequeue from an empty queue
````
[GO BACK - QUEUE Main](1-Queue.md)

[NEXT - QUEUE - Peek](1-Queue-Oper-3.md)