# Trees Operations
## Search

Search in a tree involves finding a specific node or value within the tree. It allows us to determine whether a particular element exists in the tree and locate its position if it does. The search operation typically involves traversing the tree and comparing the values of nodes to the target value.

Let's review an example of searching for a value in a binary search tree (BST):

````python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

class BST:
    def __init__(self):
        self.root = None

    def search(self, value):
        return self._search_recursive(self.root, value)

    def _search_recursive(self, current_node, value):
        if current_node is None or current_node.data == value:
            return current_node

        if value < current_node.data:
            return self._search_recursive(current_node.left, value)
        else:
            return self._search_recursive(current_node.right, value)
````            
We define a Node class to represent individual nodes in the binary search tree (BST), and a BST class that manages the tree structure.

The search method in the BST class handles the search operation. It takes a value to search for as a parameter and uses the _search_recursive method to perform the search recursively.

The _search_recursive method recursively traverses the tree, comparing the value being searched with the data of each node encountered. If the value matches the current node's data, the method returns the node. If the value is less than the current node's data, the method continues searching in the left subtree. If the value is greater, the method continues searching in the right subtree. The search continues until either the value is found or a leaf node (end of a branch) is reached, indicating that the value does not exist in the tree.

````python
tree = BST()

# Create the tree structure
tree.root = Node(5)
tree.root.left = Node(3)
tree.root.right = Node(7)
tree.root.left.left = Node(2)
tree.root.left.right = Node(4)
tree.root.right.left = Node(6)
tree.root.right.right = Node(8)

# Search for a value
result = tree.search(4)
if result:
    print("Value found!")
else:
    print("Value not found!")
````
In this case, we create an instance of BST and construct a binary search tree with nodes and their connections. We then call the search method to search for the value 4. The search operation checks whether the value exists in the tree and returns the corresponding node if found, or None if not found. Based on the result, we print an appropriate message.




[GO BACK - TREES Main](3-Tree.md)

[NEXT - TREES - Binary Search Trees](3-Tree-App-1.md)