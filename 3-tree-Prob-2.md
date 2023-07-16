# Problem Solve
## Excercise 2: 
You are given a binary tree represented by its root node. Write the validate_bst, validate_bst_recursive, and is_valid_bst functions to determine if the binary tree is a binary search tree (BST).

````python
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

class Tree:
    def __init__(self):
        self.root = None
        self.prev_value = None

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
        #Your code goes here

    def _validate_bst_recursive(self, current_node):
        #Your code goes here

def is_valid_bst(root):
    #Your code goes here

# Helper function to perform in-order traversal
def in_order_traversal(node):
    if node is None:
        return []

    return (
        in_order_traversal(node.left)
        + [node.value]
        + in_order_traversal(node.right)
    )

# Test the function
root = Node(4)
root.left = Node(2)
root.right = Node(6)
root.left.left = Node(1)
root.left.right = Node(3)
root.right.left = Node(5)
root.right.right = Node(7

````

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
        self.prev_value = None

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
        self.prev_value = None
        return self._validate_bst_recursive(self.root)

    def _validate_bst_recursive(self, current_node):
        if current_node is None:
            return True

        if not self._validate_bst_recursive(current_node.left):
            return False

        if self.prev_value is not None and current_node.value <= self.prev_value:
            return False

        self.prev_value = current_node.value

        return self._validate_bst_recursive(current_node.right)

def is_valid_bst(root):
    tree = Tree()
    values = in_order_traversal(root)
    for value in values:
        tree.insert(value)

    return tree.validate_bst()

# Helper function to perform in-order traversal
def in_order_traversal(node):
    if node is None:
        return []

    return (
        in_order_traversal(node.left)
        + [node.value]
        + in_order_traversal(node.right)
    )

# Test the function
root = Node(4)
root.left = Node(2)
root.right = Node(6)
root.left.left = Node(1)
root.left.right = Node(3)
root.right.left = Node(5)
root.right.right = Node(7

````
</details>