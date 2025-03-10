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
