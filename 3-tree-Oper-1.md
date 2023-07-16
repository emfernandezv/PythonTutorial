# Trees Operations
## Insertion

Insertion in a tree involves adding a new node to the existing tree structure. The new node can be inserted as a child of an existing node or as the root of the tree. The insertion operation requires considering the positioning and connections between nodes to maintain the hierarchical structure of the tree.

Let's review an example of inserting a new node into a binary tree::
````python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

class BinaryTree:
    def __init__(self):
        self.root = None

    def insert(self, data):
        if self.root is None:
            self.root = Node(data)
        else:
            self._insert_recursive(self.root, data)

    def _insert_recursive(self, current_node, data):
        if data < current_node.data:
            if current_node.left is None:
                current_node.left = Node(data)
            else:
                self._insert_recursive(current_node.left, data)
        else:
            if current_node.right is None:
                current_node.right = Node(data)
            else:
                self._insert_recursive(current_node.right, data)

````
We define a Node class to represent individual nodes in the binary tree, and a BinaryTree class that manages the tree structure.

The insert method in the BinaryTree class handles the insertion operation. If the tree is empty (i.e., self.root is None), the new node becomes the root of the tree. Otherwise, the insertion is performed recursively using the _insert_recursive method.

The _insert_recursive method recursively traverses the tree from the current node to find the appropriate position for the new node based on the value being inserted. If the value is less than the current node's data, it goes to the left subtree; otherwise, it goes to the right subtree. If the corresponding child node is None, a new node is created and assigned as the child. Otherwise, the method continues traversing deeper into the subtree until an appropriate position is found.

````python
tree = BinaryTree()

tree.insert(5)
tree.insert(3)
tree.insert(7)
tree.insert(2)
tree.insert(4)
tree.insert(6)
tree.insert(8)
````
In this case, we create an instance of BinaryTree and insert several values into the tree using the insert method. The insertion operation ensures that the values are placed in the correct positions based on their comparisons with existing nodes, maintaining the binary tree structure.

[GO BACK - TREES Main](3-Tree.md)

[NEXT - TREES - Deletion](3-Tree-Oper-2.md)