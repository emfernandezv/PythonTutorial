# Introduction to Trees
## Definition

A tree is a widely used hierarchical data structure that resembles a real-world tree. In computer science, a tree structure consists of nodes connected by edges, where each node can have zero or more child nodes. The topmost node in a tree is called the root, and the nodes at the bottom with no children are known as leaf nodes. Trees provide an organized way to represent hierarchical relationships between data.
## Characteristics
A tree is an abstract data type that represents a hierarchical structure with nodes and edges. It consists of the following characteristics:

* **Root:** The topmost node of the tree from which all other nodes are descendants.
* **Node:** Each element in the tree that contains data and references to its child nodes.
* **Edge:** A connection between two nodes that represents a relationship.
* **Parent:** The node that has child nodes connected to it.
* **Child:** The nodes directly connected to a parent node.
* **Leaf:** The nodes with no child nodes.
* **Path:** A sequence of connected edges between two nodes.
* **Depth:** The level of a node in the tree, where the root node is at depth 0.
* **Height:** The maximum depth of any node in the tree.
* **Subtree:** A smaller tree formed by considering a node and all its descendants.

## Types of Trees
There are various types of trees based on their characteristics and relationships. Some commonly used types include:

* **Binary Tree:** A tree where each node has at most two child nodes, namely the left child and the right child.
* **Binary Search Tree (BST):** A binary tree where the values of all nodes in the left subtree are less than the value of the root node, and the values of all nodes in the right subtree are greater than the value of the root node.
* **Balanced Tree:** A tree where the height of the left and right subtrees of any node differs by at most one, ensuring the tree remains balanced.
* **B-tree:** A self-balancing tree structure that maintains sorted data and is commonly used in databases and file systems.
* **Trie:** A tree-like structure used for efficient retrieval of strings, typically used in applications such as autocomplete and spell checking.
* **Heap:** A complete binary tree that satisfies the heap property, where each parent node is either greater than or equal to (in a max heap) or less than or equal to (in a min heap) its child nodes.
* **AVL Tree:** A self-balancing binary search tree where the heights of the left and right subtrees of any node differ by at most one.


[GO BACK - TREES Main](3-Tree.md)

[NEXT - TREES - Node Classd](3-Tree-Imp-1.md)