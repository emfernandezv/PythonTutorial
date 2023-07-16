# Implementing a Queue
## Array-based implementation
An array-based implementation of a queue is a way to represent a queue data structure using an array (also known as a list) in Python. In this implementation, the elements of the queue are stored in a fixed-size array, and additional elements are added or removed by manipulating the array index.

Here's how the array-based implementation works:

The queue is represented by an array with a fixed size. This array can store elements of the queue in sequential order.
The front of the queue is represented by an index that points to the first element in the array, and the rear of the queue is represented by an index that points to the last element.
Initially, both the front and rear indices are set to -1 to indicate an empty queue.

When an element is enqueued (added) to the queue, the rear index is incremented by 1, and the element is placed at the new rear index in the array.

When an element is dequeued (removed) from the queue, the front index is incremented by 1, and the element at the current front index is returned.
The array-based implementation allows efficient enqueue and dequeue operations with a constant time complexity of O(1). However, it has a fixed size and may need to resize the array if the queue becomes full.
Overall, the array-based implementation provides a simple and efficient way to implement a queue data structure using an array, making it suitable for scenarios where the size of the queue is known or can be estimated in advance.

Here an example:

````python
class Queue:
    def __init__(self):
        self.queue = []

    def is_empty(self):
        return len(self.queue) == 0

    def enqueue(self, data):
        self.queue.append(data)

    def dequeue(self):
        if self.is_empty():
            return None
        else:
            return self.queue.pop(0)
````

In the array-based implementation, we use a Python list to store the elements of the queue. The Queue class provides methods to enqueue and dequeue elements using the append and pop functions, respectively.

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

[NEXT - QUEUE - Linked list-based implementation](1-Queue-Imp-2.md)