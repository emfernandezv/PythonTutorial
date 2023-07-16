# Linked List Operations
## Deletion
To delete a node from the linked list, we'll define the delete method. This method will take the data value of the node to be deleted and remove it from the list.

````python
Copy code
def delete(self, data):
    if self.head is None:
        return
    
    if self.head.data == data:
        self.head = self.head.next
        return
    
    current = self.head
    while current.next:
        if current.next.data == data:
            current.next = current.next.next
            return
        current = current.next
````
In the delete method, we handle two cases: deleting the head node and deleting a non-head node. If the head node contains the data value to be deleted, we update the head attribute to skip the current head node and point to the next node. Otherwise, we iterate through the list until we find the node to be deleted. Once found, we update the next attribute of the previous node to skip the node to be deleted and maintain the linkage.

[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Search](2-LinkedList-Oper-3.md)