# Common Linked List Applications
## Stacks and Queues

Linked lists are versatile data structures that find applications in various scenarios. Let's explore two common applications of linked lists: stacks and queues.

### Stacks
A stack is a data structure that follows the Last-In-First-Out (LIFO) principle. Linked lists provide an efficient underlying structure for implementing stacks. The top element of the stack corresponds to the head node of the linked list.

Stacks support two primary operations:

* **Push:** Adds an element to the top of the stack.
* **Pop:** Removes and returns the top element from the stack.

Here's an example of itsimplementation:

````python
class Stack:
    def __init__(self):
        self.head = None
    
    def push(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node
    
    def pop(self):
        if self.head is None:
            return None
        popped_data = self.head.data
        self.head = self.head.next
        return popped_data
````
In this example, the push method inserts a new node at the head of the linked list, effectively adding an element to the top of the stack. The pop method removes the head node from the linked list and returns its data, simulating the behavior of popping an element from the stack.

### Queues

A queue is a data structure that follows the First-In-First-Out (FIFO) principle. Linked lists can be used to implement queues efficiently. The front element of the queue corresponds to the head node of the linked list, while the rear element corresponds to the tail node.

Queues support two primary operations:

* **Enqueue:** Adds an element to the rear of the queue.
* **Dequeue:** Removes and returns the front element from the queue.

Here's an example of its implementation:

````python
class Queue:
    def __init__(self):
        self.head = None
        self.tail = None
    
    def enqueue(self, data):
        new_node = Node(data)
        if self.tail is None:
            self.head = new_node
            self.tail = new_node
        else:
            self.tail.next = new_node
            self.tail = new_node
    
    def dequeue(self):
        if self.head is None:
            return None
        dequeued_data = self.head.data
        self.head = self.head.next
        if self.head is None:
            self.tail = None
        return dequeued_data
````
In this implementation, the enqueue method adds a new node at the tail of the linked list, effectively adding an element to the rear of the queue. The dequeue method removes the head node from the linked list and returns its data, simulating the behavior of dequeuing an element from the queue.

### Example 
Let's see an example of using a linked list to implement a stack and a queue:

````python
# Stack example
my_stack = Stack()
my_stack.push(10)
my_stack.push(20)
my_stack.push(30)

popped_element = my_stack.pop()
print("Popped element:", popped_element)
````

In the stack example, we create a stack my_stack, push three elements onto it, and then pop an element from the stack. The popped element is printed as the output.

````python
# Queue example
my_queue = Queue()
my_queue.enqueue(5)
my_queue.enqueue(10)
my_queue.enqueue(15)

dequeued_element = my_queue.dequeue()
print("Dequeued element:", dequeued_element)
````

In the queue example, we create a queue my_queue, enqueue three elements, and then dequeue an element from the queue. The dequeued element is printed as the output.

[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Hash Tables](2-LinkedList-App-2.md)