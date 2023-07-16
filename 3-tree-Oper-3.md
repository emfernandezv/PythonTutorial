# Trees Operations
## Traversal (In-order, Pre-order, Post-order)

Traversal in a tree involves visiting all the nodes in the tree in a specific order. It allows us to access or process the data in the nodes in a systematic manner. There are three common types of tree traversal techniques: pre-order, in-order, and post-order traversal.


Let's review an example of in-order traversal for a binary tree:

````python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

class BinaryTree:
    def __init__(self):
        self.root = None

    def inorder_traversal(self):
        if self.root is not None:
            self._inorder_recursive(self.root)

    def _inorder_recursive(self, current_node):
        if current_node is not None:
            self._inorder_recursive(current_node.left)
            print(current_node.data)
            self._inorder_recursive(current_node.right)

````
We define a Node class to represent individual nodes in the binary tree, and a BinaryTree class that manages the tree structure.

The inorder_traversal method in the BinaryTree class performs the in-order traversal of the tree. It calls the _inorder_recursive method and passes the root node as the starting point for traversal.

The _inorder_recursive method recursively traverses the tree in an in-order manner, following the pattern of left subtree, current node, and then right subtree. For each recursive call, it first traverses the left subtree, then visits the current node (prints the data in this example), and finally traverses the right subtree.

````python
tree = BinaryTree()

# Create the tree structure
tree.root = Node(4)
tree.root.left = Node(2)
tree.root.right = Node(6)
tree.root.left.left = Node(1)
tree.root.left.right = Node(3)
tree.root.right.left = Node(5)
tree.root.right.right = Node(7)

# Perform in-order traversal
tree.inorder_traversal()
````
In this case, we create an instance of BinaryTree and construct a binary tree with nodes and their connections. We then call the inorder_traversal method, which performs the in-order traversal and prints the data of each node in the tree in the specified order.

[GO BACK - TREES Main](3-Tree.md)

[NEXT - TREES - Search](3-Tree-Oper-4.md)