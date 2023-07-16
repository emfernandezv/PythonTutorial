# Problem Solve
## Excercise 1: Remove Duplicates from a Linked List

Write a function remove_duplicates that takes a linked list as input and removes any duplicate elements, keeping only the first occurrence of each unique element. The function should modify the original linked list in-place and return the updated head node.

````python
# Given linked list: 1 -> 2 -> 3 -> 2 -> 4 -> 1 -> None
# After removing duplicates: 1 -> 2 -> 3 -> 4 -> None

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def remove_duplicates(head):
#YOUR CODE STARTS HERE


#TESTING ZONE
# Create the linked list
head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(2)
fifth = Node(4)

head.next = second
second.next = third
third.next = fourth
fourth.next = fifth

# Remove duplicates from the linked list
updated_head = remove_duplicates(head)

# Traverse the updated linked list and print its elements
current = updated_head
while current is not None:
    print(current.data)
    current = current.next

# Given linked list: 1 -> 2 -> 3 -> 2 -> 4 -> 1 -> None
# After removing duplicates: 1 -> 2 -> 3 -> 4 -> None
````
Compare your code:
<details markdown="1">
<summary>Solution</summary>
<br>

````python
# Given linked list: 1 -> 2 -> 3 -> 2 -> 4 -> 1 -> None
# After removing duplicates: 1 -> 2 -> 3 -> 4 -> None

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def remove_duplicates(head):
    if head is None:
        return head

    visited = set()
    visited.add(head.data)

    current = head

    while current.next is not None:
        if current.next.data in visited:
            current.next = current.next.next
        else:
            visited.add(current.next.data)
            current = current.next

    return head

# Create the linked list
head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(2)
fifth = Node(4)

head.next = second
second.next = third
third.next = fourth
fourth.next = fifth

# Remove duplicates from the linked list
updated_head = remove_duplicates(head)

# Traverse the updated linked list and print its elements
current = updated_head
while current is not None:
    print(current.data)
    current = current.next

````
</details>

[GO BACK - LINKED LIST Main](2-LinkedList.md)
