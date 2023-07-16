# Problem Solve
## Excercise 1: 

You are given a list of integers. Write the code of the  insert and insert_recursive functions to determine if the list of integers can be rearranged to form a valid Binary Search Tree (BST).

````python
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

class Tree:
    def __init__(self):
        self.root = None

    def insert(self, value):
       #Your code goes here

    def _insert_recursive(self, current_node, value):
        #Your code goes here

    def validate_bst(self):
        return self._validate_bst_recursive(self.root, float('-inf'), float('inf'))

    def _validate_bst_recursive(self, current_node, min_value, max_value):
        if current_node is None:
            return True

        if current_node.value <= min_value or current_node.value >= max_value:
            return False

        return (self._validate_bst_recursive(current_node.left, min_value, current_node.value) and
                self._validate_bst_recursive(current_node.right, current_node.value, max_value))

def can_rearrange_to_bst(lst):
    tree = Tree()
    for value in lst:
        tree.insert(value)

    return tree.validate_bst()

# Test the function
input_list = [5, 3, 7, 2, 4, 6, 8]
result = can_rearrange_to_bst(input_list)
print(result)  # Output: True

input_list = [5, 3, 7, 2, 4, 8, 6]
result = can_rearrange_to_bst(input_list)
print(result)  # Output: False

````

Compare your code:
<details markdown="1">
<summary>Solution</summary>
<br>

````python
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

class Tree:
    def __init__(self):
        self.root = None

    def insert(self, value):
        if self.root is None:
            self.root = Node(value)
        else:
            self._insert_recursive(self.root, value)

    def _insert_recursive(self, current_node, value):
        if value < current_node.value:
            if current_node.left is None:
                current_node.left = Node(value)
            else:
                self._insert_recursive(current_node.left, value)
        else:
            if current_node.right is None:
                current_node.right = Node(value)
            else:
                self._insert_recursive(current_node.right, value)

    def validate_bst(self):
        return self._validate_bst_recursive(self.root, float('-inf'), float('inf'))

    def _validate_bst_recursive(self, current_node, min_value, max_value):
        if current_node is None:
            return True

        if current_node.value <= min_value or current_node.value >= max_value:
            return False

        return (self._validate_bst_recursive(current_node.left, min_value, current_node.value) and
                self._validate_bst_recursive(current_node.right, current_node.value, max_value))

def can_rearrange_to_bst(lst):
    tree = Tree()
    for value in lst:
        tree.insert(value)

    return tree.validate_bst()

# Test the function
input_list = [5, 3, 7, 2, 4, 6, 8]
result = can_rearrange_to_bst(input_list)
print(result)  # Output: True

input_list = [5, 3, 7, 2, 4, 8, 6]
result = can_rearrange_to_bst(input_list)
print(result)  # Output: False

````
</details>



[GO BACK - TREES Main](3-Tree.md)
