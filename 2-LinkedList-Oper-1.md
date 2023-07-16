# Linked List Operations
## Insertion
To insert a new node into the linked list, we'll define the insert method. This method will take the data value as an argument and add a new node to the beginning of the list.

````python
def insert(self, data):
    new_node = Node(data)
    new_node.next = self.head
    self.head = new_node
````
In the insert method, we create a new node with the provided data. We set the next attribute of the new node to the current head node, effectively linking the new node to the rest of the list. Finally, we update the head attribute to point to the new node, making it the first node in the list.

[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Deletion](2-LinkedList-Oper-2.md)