# Implementing Trees
## Node Class
The Node class represents a single node in the tree and typically contains the following attributes:

* **_init_(self, data):** This is the constructor method that gets called when creating a new node object. It takes a parameter data to initialize the data stored in the node. The data can be of any type (e.g., integer, string, object) and represents the value associated with the node.

* **self.data:** This is an instance variable that stores the value or data associated with the node. It holds the actual information or payload that we want to store in the node.

* **self.children:** This is a list that holds references to the child nodes of the current node. Since a node in a tree can have zero or more child nodes, we use a list to store these references. By default, we initialize it as an empty list using self.children = [].

````python

class Node:
    def __init__(self, data):
        self.data = data
        self.children = []
````
By creating instances of the Node class and connecting them through their children list, we can build complex tree structures. Each node holds its own data and references to its child nodes, allowing us to traverse the tree and perform various operations.

Let's review an example:

````python
# Create nodes
root = Node("A")
child1 = Node("B")
child2 = Node("C")
child3 = Node("D")

# Connect nodes
root.children.append(child1)
root.children.append(child2)
child2.children.append(child3)
````
We create four nodes with data "A", "B", "C", and "D". We set "A" as the root node, and then we connect the other nodes as its children using the children list. Here, "B" and "C" are children of "A", and "D" is a child of "C". This structure represents a simple tree hierarchy.

[GO BACK - TREES Main](3-Tree.md)

[NEXT - TREES - Tree Classd](3-Tree-Imp-2.md)