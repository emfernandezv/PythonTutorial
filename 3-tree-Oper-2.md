# Trees Operations
## Deletion
Deletion in a tree involves removing a node from the existing tree structure. The deletion operation requires considering different scenarios, such as the location of the node to be deleted (whether it is a leaf node, a node with one child, or a node with two children) and adjusting the connections between the remaining nodes to maintain the integrity of the tree.

Let's review an example of deleting a node from a binary search tree:
````python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

class BST:
    def __init__(self):
        self.root = None

    def delete(self, data):
        self.root = self._delete_recursive(self.root, data)

    def _delete_recursive(self, current_node, data):
        if current_node is None:
            return current_node

        if data < current_node.data:
            current_node.left = self._delete_recursive(current_node.left, data)
        elif data > current_node.data:
            current_node.right = self._delete_recursive(current_node.right, data)
        else:
            if current_node.left is None:
                return current_node.right
            elif current_node.right is None:
                return current_node.left

            min_node = self._find_min(current_node.right)
            current_node.data = min_node.data
            current_node.right = self._delete_recursive(current_node.right, min_node.data)

        return current_node

    def _find_min(self, node):
        current = node
        while current.left is not None:
            current = current.left
        return current

````
 we define a Node class to represent individual nodes in the binary search tree (BST), and a BST class that manages the tree structure.

The delete method in the BST class handles the deletion operation. It takes the data value of the node to be deleted as a parameter and uses the _delete_recursive method to perform the deletion recursively.

The _delete_recursive method recursively traverses the tree to find the node with the given data value. If the data value is less than the current node's data, it continues searching in the left subtree. If the data value is greater, it continues searching in the right subtree. If the data value is equal to the current node's data, it handles different scenarios:

* If the node has no children, it simply removes the node.
* If the node has only one child, it replaces the node with its child.
* If the node has two children, it finds the minimum node in the right subtree (which will be the successor of the node), replaces the node's data with the minimum node's data, and recursively deletes the minimum node from the right subtree.

The _find_min method finds the minimum node in a given subtree by traversing to the leftmost node of the subtree.

````python
tree = BST()

tree.insert(5)
tree.insert(3)
tree.insert(7)
tree.insert(2)
tree.insert(4)
tree.insert(6)
tree.insert(8)

tree.delete(4)
tree.delete(7)
````
In this case, we create an instance of BST and insert several values into the tree using the insert method. We then perform deletion operations by calling the delete method, providing the data value of the nodes to be deleted. The deletion operation adjusts the connections and removes the specified nodes while maintaining the binary search tree property.

[GO BACK - TREES Main](3-Tree.md)

[NEXT - TREES - Traversal](3-Tree-Oper-3.md)