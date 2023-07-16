# Common Trees Applications
## Binary Search Trees (BST)

A Binary Search Tree (BST) is a type of binary tree that satisfies a specific property: for each node, all the values in its left subtree are smaller than its value, and all the values in its right subtree are greater. This property allows for efficient searching, insertion, and deletion of elements in the tree.

Binary Search Trees have various applications in computer science and can be used in scenarios where efficient searching and maintaining sorted data are important. Here are a few common applications of Binary Search Trees:

* **Efficient Searching:** The BST property allows for efficient searching of elements. By comparing the value being searched with the values in the nodes during traversal, the search operation can quickly navigate to the desired element or determine its absence in the tree.

* **Sorted Data Storage:** Binary Search Trees naturally maintain the elements in sorted order. The left subtree of each node contains values smaller than the node, while the right subtree contains values greater. This property makes BSTs useful for scenarios where data needs to be stored and accessed in a sorted manner.

* **Range Queries:** BSTs enable range queries, which involve searching for elements within a given range. By leveraging the BST property, range queries can be efficiently performed by examining the values in the nodes and selectively traversing the appropriate subtrees.

* **Symbol Table:** BSTs can be used to implement symbol tables, which associate keys with values. In a BST-based symbol table, the keys are stored in the tree, and the associated values can be accessed or updated based on the key. The BST structure allows for efficient key lookup and modification operations.

* **Dictionary Implementation:** BSTs can serve as the underlying data structure for dictionary implementations. The keys can be stored in the BST, allowing for efficient retrieval and modification of key-value pairs.

Let's review an example:
````markdown
                         4
                       /   \
                      2     6
                     / \   / \
                    1   3 5   7
````
we have a BST with integer values. The root of the tree is 4, and its left subtree contains values 2, 1, and 3, while the right subtree contains values 6, 5, and 7.

````python
#code to create and traverse the above BST
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

def inorder_traversal(node):
    if node is not None:
        inorder_traversal(node.left)
        print(node.value)
        inorder_traversal(node.right)

# Constructing the BST
root = Node(4)
root.left = Node(2)
root.right = Node(6)
root.left.left = Node(1)
root.left.right = Node(3)
root.right.left = Node(5)
root.right.right = Node(7)

# Perform in-order traversal
inorder_traversal(root)

````
This code creates a BST using the Node class, where each node stores a value and has left and right child pointers. The inorder_traversal function performs an in-order traversal of the tree, which prints the values of the nodes in ascending order.

The result of the code would be:
````
1
2
3
4
5
6
7
````
The output demonstrates the in-order traversal, which visits the nodes in ascending order according to the BST property.

To use the benefits of Binary Search Trees, it is important to maintain the BST property during tree operations such as insertion and deletion. By ensuring that the tree remains balanced and the ordering property is preserved, the efficiency of these applications can be maximized.




[GO BACK - TREES Main](3-Tree.md)

[NEXT - TREES - Expression Trees](3-Tree-App-2.md)