# Common Queue Applications
##  BFS - Breadth-First Search
BFS (Breadth-First Search) is a graph traversal algorithm that explores all the vertices of a graph in breadth-first order. It starts at a given source vertex and visits its neighboring vertices before moving on to the next level of vertices.

Here's a simplified explanation of the BFS algorithm using easy-to-understand language:

1. Start by selecting a source vertex to begin the traversal.
2. Initialize an empty queue and enqueue the source vertex into it.
3. Create a visited set to keep track of the visited vertices.
4. While the queue is not empty, do the following:
   * Dequeue a vertex from the front of the queue.
   * Mark the dequeued vertex as visited.
   * Process the vertex (e.g., print its value or perform an operation).
   * Enqueue all the unvisited neighboring vertices of the current vertex into the queue.
   * Mark the enqueued vertices as visited to avoid processing them multiple times.

5. Repeat step 4 until all vertices are visited.

The BFS algorithm explores the graph level by level, visiting vertices in a breadth-first manner. This ensures that all vertices at a given level are visited before moving on to the next level. It guarantees that the algorithm visits all vertices reachable from the source vertex and finds the shortest path between the source and any other reachable vertex.

Here an example:
````python
from collections import deque

def bfs(graph, source):
    visited = set()
    queue = deque()
    queue.append(source)
    visited.add(source)

    while queue:
        vertex = queue.popleft()
        print(vertex)  # Process the vertex (e.g., print its value)

        for neighbor in graph[vertex]:
            if neighbor not in visited:
                queue.append(neighbor)
                visited.add(neighbor)
````
In this example, we have a graph represented as an adjacency list. The bfs function takes the graph and a source vertex as parameters. It initializes an empty set visited to store visited vertices and a deque object queue to perform the breadth-first traversal.

The BFS algorithm starts by enqueuing the source vertex into the queue and marking it as visited. Then, it enters the main loop and continues until the queue is empty. In each iteration, it dequeues a vertex from the front of the queue, processes the vertex (prints its value in this example), and enqueues all the unvisited neighboring vertices into the queue while marking them as visited.

We can test using:
````python
# Example graph represented as an adjacency list
graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': ['F'],
    'F': []
}

# Perform BFS traversal starting from vertex 'A'
bfs(graph, 'A') # Result: A, B, C, D, E, F
````
[GO BACK - QUEUE Main](1-Queue.md)

[NEXT - QUEUE - Job Scheduling](1-Queue-App-2.md)