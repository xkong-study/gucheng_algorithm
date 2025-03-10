### **Graph Fundamentals (图基础)**

- "A graph is a data structure that consists of nodes (vertices) and edges connecting them."
- "Graphs can be either directed or undirected, weighted or unweighted."
- "A common way to represent a graph is using an adjacency list or an adjacency matrix."
- "Depth-first search (DFS) and breadth-first search (BFS) are two fundamental graph traversal techniques."

### **BFS and DFS (BFS 和 DFS)**

- "BFS explores nodes level by level, making it ideal for finding the shortest path in an unweighted graph."
- "DFS explores as deep as possible before backtracking, which is useful for cycle detection and pathfinding."
- "BFS is implemented using a queue, while DFS is implemented using recursion or an explicit stack."
- "A key difference between BFS and DFS is their space complexity; BFS can use more memory in wide graphs."

### **Shortest Path (最短路径)**

- "To find the shortest path in an unweighted graph, BFS is the optimal choice."
- "For weighted graphs, Dijkstra’s algorithm is commonly used when all weights are positive."
- "The Bellman-Ford algorithm can handle negative weights, but it has higher time complexity."
- "Floyd-Warshall is useful for finding shortest paths between all pairs of nodes."

### **Matrix as Graph (矩阵作为图)**

- "A 2D matrix can be treated as a graph where each cell is a node and adjacent cells are connected by edges."
- "Flood fill algorithms, such as BFS or DFS, are used for problems like 'Number of Islands'."
- "In 'Walls and Gates', BFS is used to propagate distances from gates to empty rooms."
- "The 'Knight’s Minimum Moves' problem can be solved using BFS due to its unweighted nature."

### **Implicit Graph (隐式图)**

- "Implicit graphs are not explicitly stored but can be derived from problem constraints."
- "Problems like 'Open the Lock' or 'Sliding Puzzle' involve state transitions that form an implicit graph."
- "These problems are often solved using BFS to explore the minimum steps to reach a target state."
- "The 'Word Ladder' problem can be represented as a graph where words are nodes and edges exist between words that differ by one letter."

### **Topological Sort (拓扑排序)**

- "Topological sorting is applicable to directed acyclic graphs (DAGs)."
- "It helps determine the order of tasks with dependencies, such as course scheduling."
- "Kahn’s algorithm (BFS-based) and DFS-based approaches are two ways to perform topological sorting."
- "If a cycle is detected in a directed graph, a valid topological order does not exist."

### **Weighted Graph (加权图)**

- "Dijkstra’s algorithm finds the shortest path in a weighted graph with non-negative edges."
- "The priority queue (min-heap) is commonly used to optimize Dijkstra’s algorithm to O((V + E) log V)."
- "The Bellman-Ford algorithm is used when negative weights are present, though it runs in O(VE) time."
- "The Floyd-Warshall algorithm finds all-pairs shortest paths in O(V³) time."

### **Minimum Spanning Tree (最小生成树)**

- "A Minimum Spanning Tree (MST) is a subset of edges that connects all nodes with the minimum total weight."
- "Kruskal’s algorithm sorts edges and uses union-find to construct the MST efficiently."
- "Prim’s algorithm uses a priority queue (min-heap) to expand the MST from an arbitrary starting node."
- "MSTs are useful in network design, such as laying out electrical grids or optimizing road networks."

## **Graph Traversal (BFS & DFS)**

### **Approach**

- Use **BFS** for shortest path problems in unweighted graphs (e.g., Number of Islands, Knight's Minimum Moves).
- Use **DFS** for connected component searches, pathfinding, or cycle detection (e.g., Flood Fill).
- Use a **visited set or array** to prevent revisiting nodes and avoid infinite loops.
- For **directed graphs**, check for **cycles** (e.g., Course Schedule).

### **Interview Phrases**

- "I will use BFS because this is an unweighted shortest path problem."
- "Since we need to explore all connected components, DFS is a good choice."
- "To avoid revisiting nodes, I will use a visited set."
- "For cycle detection in a directed graph, I will use the in-degree method (Kahn's Algorithm) or DFS with backtracking."
- "I will use an adjacency list representation for efficiency."

## **Shortest Path Problems**

### **Approach**

- Use **BFS** for the shortest path in an **unweighted graph**.
- Use **Dijkstra’s Algorithm** for the shortest path in a **weighted graph with non-negative edges**.
- Use **Bellman-Ford** if **negative weights** are involved.
- Use **Floyd-Warshall** for **all-pairs shortest paths**.

### **Interview Phrases**

- "Since this is an unweighted graph, BFS is the most efficient choice for finding the shortest path."
- "Dijkstra's algorithm is optimal here because all edge weights are non-negative."
- "If negative weights are present, I will use the Bellman-Ford algorithm."
- "Floyd-Warshall allows us to compute the shortest paths between all pairs of nodes efficiently."

## **Matrix as a Graph (2D Grid Problems)**

### **Approach**

- Treat the **grid as a graph**, where each cell is a node and adjacent cells are edges.
- Use **BFS** for shortest path and multi-source problems (Walls and Gates, Zombie in Matrix).
- Use **DFS** for flood-fill-type problems (Number of Islands, Flood Fill).
- Use a **queue** for BFS and **recursive calls** or **an explicit stack** for DFS.
- Consider **four or eight possible directions** for movement.

### **Interview Phrases**

- "I will treat the matrix as a graph where each cell is a node connected to its neighbors."
- "I will use BFS since we need to find the shortest path from multiple sources."
- "DFS is useful here because we need to explore entire regions before backtracking."
- "To ensure all cells are visited, I will mark them as visited once processed."

## **Implicit Graph Problems**

### **Approach**

- Convert the problem into a graph where **states are nodes** and **valid transitions are edges**.
- Use **BFS** for the shortest transformation sequence (Word Ladder, Open the Lock).
- Use **backtracking or DFS** for exhaustive searches (Sliding Puzzle).
- If the graph is too large, use **bidirectional BFS** to optimize.

### **Interview Phrases**

- "This problem can be represented as an implicit graph where each valid state is a node."
- "I will use BFS to find the shortest sequence of transformations."
- "Since the state space is large, bidirectional BFS can optimize the search."
- "Each node represents a unique configuration, and edges represent valid moves."

## **Topological Sorting (DAG Processing)**

### **Approach**

- Use **Kahn's Algorithm (BFS)** or **DFS-based topological sorting** for DAG problems.
- If there is a cycle, **topological sorting is not possible**.
- Use **in-degree** to determine the processing order (Course Schedule, Alien Dictionary).

### **Interview Phrases**

- "Since the graph is a DAG, I will use topological sorting to determine the processing order."
- "I will use Kahn’s Algorithm (BFS-based topological sort) to process nodes with zero in-degree first."
- "If a cycle is detected, the problem constraints are invalid."
- "A topological sort helps us order tasks based on dependencies."

## **Minimum Spanning Tree (MST)**

### **Approach**

- Use **Kruskal’s Algorithm** (greedy, sorts edges, uses union-find).
- Use **Prim’s Algorithm** (greedy, starts from a node and expands the MST).
- MST is useful in **network design, road planning, and clustering**.

### **Interview Phrases**

- "Since we need to find the minimum spanning tree, I will use Kruskal’s Algorithm with union-find."
- "Prim’s Algorithm is also a good choice since it expands from a given starting node."
- "Kruskal’s Algorithm sorts the edges and processes them greedily to construct the MST."
- "The MST ensures that all nodes are connected with the minimum possible edge weight."
