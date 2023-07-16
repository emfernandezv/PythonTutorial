# Implementing Trees
## Tree Class
The Tree class is a data structure that represents a hierarchical structure with a collection of connected nodes. It consists of nodes that are organized in a parent-child relationship, where each node can have zero or more child nodes. The Tree class provides a way to organize and store data in a hierarchical manner.

In the Tree class, each node typically contains two main components:

* **__init__(self, data):** This is the constructor method that gets called when creating a new tree object. It takes a parameter data to initialize the data stored in the root node of the tree. The data can be of any type (e.g., integer, string, object) and represents the value associated with the root node.

* **self.data:** This is an instance variable that stores the value or data associated with the root node of the tree. It holds the actual information or payload that we want to store in the root node.

* **self.children:** This is a list that holds references to the child nodes of the root node. Since a tree can have multiple child nodes, we use a list to store these references. By default, we initialize it as an empty list using self.children = [].

````python
class Tree:
    def __init__(self, data):
        self.data = data
        self.children = []

````


By utilizing the Tree class, we can represent various hierarchical structures and solve problems that involve organizing and manipulating data in a tree-like manner. It is a fundamental data structure used in various domains, including computer science, data analysis, and artificial intelligence.

Let's review an example:
````python
# Create the root node
tree = Tree("A")

# Create child nodes
child1 = Tree("B")
child2 = Tree("C")
child3 = Tree("D")

# Connect child nodes to the root node
tree.children.append(child1)
tree.children.append(child2)
tree.children.append(child3)
````
We first create the root node with data "A" using tree = Tree("A"). Then, we create child nodes with data "B", "C", and "D". Finally, we connect these child nodes to the root node by appending them to the children list.


[GO BACK - TREES Main](3-Tree.md)

[NEXT - TREES - Insertion](3-Tree-Oper-1.md)