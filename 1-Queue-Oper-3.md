# Queue Operations
## Peek
The peek operation in a queue allows us to look at the element that is currently at the front of the queue, without modifying or removing it. It is useful when we want to see what element will be dequeued next without actually dequeuing it. The peek operation does not change the state of the queue or its contents; it only provides us with a way to inspect the front element.

With the peek operation, we can get a glimpse of the first element in the queue without altering the order of the elements or removing them. This is helpful when we need to perform some conditional checks or access the front element temporarily before processing it further.

The peek operation is particularly useful in scenarios where we want to implement logic based on the first element in the queue, such as checking if a certain condition is met, comparing values, or performing any other operation that requires knowledge of the front element.

Overall, the peek operation provides a way to access the front element of a queue without modifying its content or order, allowing us to gather information or make decisions based on that element.

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
            print("Queue is empty")

    def peek(self):
        if not self.is_empty():
            return self.queue[0]
        else:
            print("Queue is empty")

    def is_empty(self):
        return len(self.queue) == 0
````
In this example, we define a Queue class with an array-based implementation. The enqueue method is used to add elements to the queue, the dequeue method is used to remove elements from the front of the queue, and the is_empty method checks if the queue is empty.

The peek method is used to retrieve the element at the front of the queue without removing it. It simply returns the value of the first element in the queue list. If the queue is empty, it prints the message "Queue is empty".

We create a queue object and enqueue three elements (10, 20, 30) using the enqueue method. Then, we use the peek method to retrieve the value of the front element (10) and print it. After dequeuing an element, we again use the peek method to get the value of the new front element (20) and print it.

The output of the example shows the peeked elements (10 and 20) at different stages of the queue.

We can test this using:
````python
# Creating a queue object
queue = Queue()

# Enqueueing elements
queue.enqueue(10)
queue.enqueue(20)
queue.enqueue(30)

# Peeking at the front element
print(queue.peek())  # Output: 10

# Dequeueing an element
queue.dequeue()

# Peeking at the new front element
print(queue.peek())  # Output: 20
````

[GO BACK - QUEUE Main](1-Queue.md)

[NEXT - QUEUE - BFS](1-Queue-App-1.md)