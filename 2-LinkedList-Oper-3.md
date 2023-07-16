# Linked List Operations
## Search

To search for an element in the linked list, we traverse the list and compare each node's data.

````python

def search(self, data):
    current = self.head
    while current:
        if current.data == data:
            return True
        current = current.next
    return False
````

[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Traversal](2-LinkedList-Oper-4.md)