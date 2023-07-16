# Linked List Operations
## Traversal

To traverse the linked list and print its elements, we'll define the traverse method.

````python
def traverse(self):
    current = self.head
    while current:
        print(current.data)
        current = current.next
````
The traverse method starts from the head node and iterates through the list by updating the current variable to the next node in each iteration. We print the data of each node until we reach the end of the list (current becomes None).

[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Stacks and Queues](2-LinkedList-App-1.md)