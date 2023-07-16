# Problem Solve
## Excercise 1: Reverse a Linked List

Write a function reverse_linked_list that takes a linked list as input and reverses its order. The function should modify the original linked list in-place and return the new head node.

````python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def reverse_linked_list(head):
# YOUR CODE STARTS HERE


#TEST ZONE
# Create the linked list
head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(4)

head.next = second
second.next = third
third.next = fourth

# Reverse the linked list
reversed_head = reverse_linked_list(head)

# Traverse the reversed linked list and print its elements
current = reversed_head
while current is not None:
    print(current.data)
    current = current.next

# Given linked list: 1 -> 2 -> 3 -> 4 -> None
# After reversing: 4 -> 3 -> 2 -> 1 -> None
````
Compare your code:
<details markdown="1">
<summary>Solution</summary>
<br>

````python
# Given linked list: 1 -> 2 -> 3 -> 4 -> None
# After reversing: 4 -> 3 -> 2 -> 1 -> None

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def reverse_linked_list(head):
    previous = None
    current = head

    while current is not None:
        next_node = current.next
        current.next = previous
        previous = current
        current = next_node

    return previous

# Create the linked list
head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(4)

head.next = second
second.next = third
third.next = fourth

# Reverse the linked list
reversed_head = reverse_linked_list(head)

# Traverse the reversed linked list and print its elements
current = reversed_head
while current is not None:
    print(current.data)
    current = current.next
````
</details>

[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Problem 2](2-LinkedList-Prob-2.md)