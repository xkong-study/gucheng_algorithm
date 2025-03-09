### **📌 Common English Phrases & Terms for Coding Interviews (Recursion, DFS, Backtracking, Trees, DP, and More)**

Here’s a comprehensive list of **phrases, words, and explanations** you may encounter in a coding interview, particularly when discussing **trees, recursion, DFS, backtracking, and dynamic programming**.

## **1️⃣ General Algorithm and Problem-Solving Terms**

- **Time complexity**: The amount of time an algorithm takes to run as a function of input size.
- **Space complexity**: The amount of memory an algorithm needs relative to input size.
- **Optimization**: Improving efficiency in terms of time and/or space.
- **Brute-force approach**: Trying all possible solutions to find the correct one.
- **Edge case**: A special input that may cause problems (e.g., empty input, maximum input).
- **Corner case**: An unusual case that is close to a limit or boundary.
- **Recurrence relation**: An equation that defines a sequence based on previous terms.
- **Trade-offs**: Balancing between different approaches (e.g., time vs. space).
- **Heuristic**: A practical approach that may not be optimal but works well.

## **2️⃣ Recursion & DFS (Depth-First Search)**

- **Recursive function**: A function that calls itself with a smaller problem.
- **Base case**: The stopping condition for a recursive function.
- **Recursive stack**: The stack of function calls in recursion.
- **Stack overflow**: When too many recursive calls cause the stack to exceed memory limits.
- **Backtracking**: Exploring possible solutions and undoing choices if needed.
- **Memoization**: Caching previously computed results to avoid redundant calculations.
- **Top-down approach**: Solving the problem by breaking it down into smaller subproblems recursively.
- **Bottom-up approach**: Solving subproblems first and building up to the final solution.

🔹 **Example phrases:**

- "This problem can be solved using recursion because the solution depends on smaller subproblems."
- "We need a base case to stop the recursion and prevent infinite loops."
- "We use memoization to avoid recalculating the same subproblem multiple times."
- "The recursion depth is proportional to the height of the tree."

## **3️⃣ Binary Trees & Binary Search Trees**

### **Tree Terminology**

- **Root node**: The topmost node in a tree.
- **Leaf node**: A node with no children.
- **Parent & Child**: A node directly above/below another node.
- **Sibling nodes**: Nodes that share the same parent.
- **Height of a tree**: The longest path from root to a leaf.
- **Depth of a node**: The distance from the root to that node.
- **Balanced tree**: A tree where the difference in height between left and right subtrees is at most 1.
- **Binary Search Tree (BST)**: A tree where left child < parent < right child.

🔹 **Example phrases:**

- "To find the maximum depth of a tree, we use a recursive DFS approach."
- "A balanced binary tree ensures that searching takes O(log N) time."
- "To check if a tree is a BST, we verify that every node follows the BST property."
- "The lowest common ancestor (LCA) of two nodes in a BST is the first node where the paths to both nodes diverge."

### **Common Tree Algorithms**

| **Algorithm** | **Concept** | **Time Complexity** |
| --- | --- | --- |
| **DFS on a tree** | Depth-first traversal | **O(N)** |
| --- | --- | --- |
| **BFS on a tree** | Level-order traversal | **O(N)** |
| --- | --- | --- |
| **Invert a binary tree** | Swap left and right subtrees | **O(N)** |
| --- | --- | --- |
| **Reconstruct a tree from traversals** | Build from preorder/inorder | **O(N)** |
| --- | --- | --- |
| **Check if a tree is balanced** | Recursively check subtree heights | **O(N)** |
| --- | --- | --- |
| **Find lowest common ancestor (LCA)** | Find the deepest shared ancestor | **O(N)** |
| --- | --- | --- |

## **4️⃣ Backtracking**

- **Backtracking algorithm**: A technique that tries different possibilities and undoes invalid choices.
- **State space tree**: A conceptual tree where each node represents a partial solution.
- **Pruning**: Cutting off unnecessary recursive calls to optimize performance.
- **Constraint satisfaction**: Ensuring that each choice meets a given condition.

🔹 **Example phrases:**

- "We use backtracking to generate all possible solutions and return the valid ones."
- "We can optimize the algorithm by pruning unnecessary branches in the recursion tree."
- "Backtracking is useful when we need to explore multiple possibilities, like generating all valid parentheses combinations."
- "The base case is when we reach the required length or satisfy the problem's constraints."

### **Common Backtracking Problems**

| **Problem** | **Concept** | **Time Complexity** |
| --- | --- | --- |
| **Generate permutations** | Try all orderings | **O(N!)** |
| --- | --- | --- |
| **Generate subsets** | Include/exclude each element | **O(2^N)** |
| --- | --- | --- |
| **Sudoku solver** | Fill board by constraints | **O(9^N)** |
| --- | --- | --- |
| **N-Queens** | Place queens without attacks | **O(N!)** |
| --- | --- | --- |
| **Word Break** | Break words using dictionary | **O(2^N) -> O(N) with DP** |
| --- | --- | --- |

## **5️⃣ Dynamic Programming (DP)**

- **Overlapping subproblems**: The problem can be broken into smaller problems that repeat.
- **Optimal substructure**: The solution to a problem can be built from smaller solutions.
- **Memoization**: Storing computed results to reuse later.
- **Tabulation**: Using an array to build the solution iteratively.
- **Knapsack problem**: Choosing items with weight constraints to maximize value.

🔹 **Example phrases:**

- "We use dynamic programming to avoid recomputing the same subproblems."
- "The optimal substructure property allows us to build a solution from previously computed values."
- "We store results in a table (bottom-up approach) instead of using recursion."
- "This problem can be solved with memoization to improve efficiency."

### **Common DP Problems**

| **Problem** | **Concept** | **Time Complexity** |
| --- | --- | --- |
| **Fibonacci sequence** | Recursion with memoization | **O(N)** |
| --- | --- | --- |
| **Coin change** | Min coins for amount | **O(N \* M)** |
| --- | --- | --- |
| **Longest common subsequence** | Find the longest matching subsequence | **O(N \* M)** |
| --- | --- | --- |
| **Climbing stairs** | Ways to reach step **n** | **O(N)** |
| --- | --- | --- |

## **6️⃣ Complexity & Performance Analysis**

- **Asymptotic analysis**: Studying how an algorithm's performance grows.
- **Big-O notation**: Describes the worst-case runtime.
- **Amortized time complexity**: Average performance over multiple operations.
- **Trade-off between time and space**: Faster algorithms may use more memory.
- **Best-case vs. worst-case vs. average-case complexity**.

🔹 **Example phrases:**

- "The worst-case time complexity of this algorithm is O(N²) due to nested loops."
- "By using a heap, we can reduce sorting time complexity to O(N log N)."
- "The space complexity is O(N) because we store intermediate results."
- "This algorithm runs in constant time O(1) since it only performs a fixed number of operations."

### **🎯 Summary**

| **Category** | **Key Concepts** |
| --- | --- |
| **Recursion & DFS** | Base case, recursive stack, memoization |
| --- | --- |
| **Trees & BST** | Root, leaf, height, inorder/preorder/postorder traversal |
| --- | --- |
| **Backtracking** | State space tree, pruning, constraint satisfaction |
| --- | --- |
| **Dynamic Programming** | Memoization, tabulation, overlapping subproblems |
| --- | --- |
| **Complexity Analysis** | O(1), O(log N), O(N), O(N log N), O(N²), O(2^N), O(N!) |
| --- | --- |

🚀 **Mastering these terms will help you confidently discuss your thought process in interviews!** 🚀
