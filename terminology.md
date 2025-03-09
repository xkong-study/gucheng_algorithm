### **📌 Key Math Concepts for Technical Interviews**

This is a **quick reference guide** covering the essential math concepts you need for **coding interviews**.

## **1️⃣ Number Bases**

| **Term** | **Definition** | **Common Uses** |
| --- | --- | --- |
| **Base 10 (Decimal System)** | Uses digits 0-9, natural for humans | Everyday calculations |
| --- | --- | --- |
| **Base 2 (Binary System)** | Uses only 0 and 1 | Computers, bitwise operations |
| --- | --- | --- |
| **Base 16 (Hexadecimal System)** | Uses digits 0-9 and A-F | Memory addresses, color codes |
| --- | --- | --- |

🔹 **Example: Binary to Decimal Conversion** Binary 1011 → 1×23+0×22+1×21+1×20=8+0+2+1=111 \\times 2^3 + 0 \\times 2^2 + 1 \\times 2^1 + 1 \\times 2^0 = 8 + 0 + 2 + 1 = 111×23+0×22+1×21+1×20=8+0+2+1=11

## **2️⃣ Logarithms & Exponents**

| **Term** | **Definition** | **Common Uses** |
| --- | --- | --- |
| **Exponentiation** | aba^bab means multiplying aaa by itself bbb times | Power calculations |
| --- | --- | --- |
| **Logarithm** | The inverse of exponentiation, answers "how many times must the base be multiplied?" | Binary search, complexity analysis |
| --- | --- | --- |
| **Binary Log (log⁡2n\\log_2 nlog2​n)** | Measures how many times nnn can be divided by 2 | **Binary search O(log⁡n)O(\\log n)O(logn), tree height** |
| --- | --- | --- |

🔹 **Example: Logarithmic Reduction**

- log⁡2(8)=3\\log_2(8) = 3log2​(8)=3 because 23=82^3 = 823=8
- log⁡2(16)=4\\log_2(16) = 4log2​(16)=4 because 24=162^4 = 1624=16

## **3️⃣ Arithmetic Sequence**

| **Term** | **Definition** | **Common Uses** |
| --- | --- | --- |
| **Arithmetic Sequence** | A sequence with a constant difference between terms | Counting loops, sum calculations |
| --- | --- | --- |
| **Arithmetic Sum Formula** | S=(a1+an)×n2S = \\frac{(a_1 + a_n) \\times n}{2}S=2(a1​+an​)×n​ | **Nested loop complexity O(n2)O(n^2)O(n2)** |
| --- | --- | --- |

🔹 **Example: Nested Loop Analysis**

js



for (let i = 0; i < n; i++) {

for (let j = 0; j <= i; j++) {

doSomething();

}

}

Total executions:

1+2+3+...+n=O(n2)1 + 2 + 3 + ... + n = O(n^2)1+2+3+...+n=O(n2)

## **4️⃣ Geometric Sequence**

| **Term** | **Definition** | **Common Uses** |
| --- | --- | --- |
| **Geometric Sequence** | A sequence where each term is multiplied by a constant ratio | **Recursive problems, binary trees** |
| --- | --- | --- |
| **Geometric Sum Formula** | S=a1×1−rn1−rS = a_1 \\times \\frac{1 - r^n}{1 - r}S=a1​×1−r1−rn​ | **Perfect binary tree node count O(log⁡n)O(\\log n)O(logn)** |
| --- | --- | --- |

🔹 **Example: Perfect Binary Tree**

yaml



Level 0: 1

Level 1: 2

Level 2: 4

Level 3: 8

...

Total nodes:

1+2+4+...+2h=2h+1−11 + 2 + 4 + ... + 2^h = 2^{h+1} - 11+2+4+...+2h=2h+1−1

**Height: O(log⁡n)O(\\log n)O(logn)**

## **5️⃣ Modular Arithmetic**

| **Term** | **Definition** | **Common Uses** |
| --- | --- | --- |
| **Modulo (Mod)** | amod  ba \\mod bamodb is the remainder of aaa divided by bbb | **Circular arrays, hash functions, cryptography** |
| --- | --- | --- |
| **Mod Distributive Property** | (a+b)mod  c=\[(amod  c)+(bmod  c)\]mod  c(a + b) \\mod c = \[(a \\mod c) + (b \\mod c)\] \\mod c(a+b)modc=\[(amodc)+(bmodc)\]modc | **Efficient large-number computations** |
| --- | --- | --- |

🔹 **Example: Clock Arithmetic**

js



15 % 12 = 3 // 15-hour clock time converts to 3 PM

🔹 **Example: Using Mod in Prime Checking**

js



function isPrime(n) {

if (n < 2) return false;

for (let i = 2; i \* i <= n; i++) {

if (n % i === 0) return false;

}

return true;

}

## **6️⃣ Combinatorics (Counting)**

| **Term** | **Definition** | **Common Uses** |
| --- | --- | --- |
| **Factorial n!n!n!** | n!=n×(n−1)×...×1n! = n \\times (n-1) \\times ... \\times 1n!=n×(n−1)×...×1 | **Permutations O(n!)O(n!)O(n!)** |
| --- | --- | --- |
| **Permutation** | Ordered arrangement of elements | **Generating all orderings** |
| --- | --- | --- |
| **Combination** | Unordered selection of elements | **Choosing subsets** |
| --- | --- | --- |
| **Subset Calculation** | 2n2^n2n total subsets of a set with nnn elements | **Subset generation O(2n)O(2^n)O(2n)** |
| --- | --- | --- |

🔹 **Example: Factorial Calculation**

js



function factorial(n) {

return n === 1 ? 1 : n \* factorial(n - 1);

}

console.log(factorial(5)); // Outputs 120

## **7️⃣ Complexity Analysis (Big-O Notation)**

| **Term** | **Definition** | **Common Uses** |
| --- | --- | --- |
| **Big-O Notation** | Represents worst-case time complexity | Algorithm analysis |
| --- | --- | --- |
| **O(1)O(1)O(1) (Constant Time)** | Fixed-time operation | **Hash table lookup** |
| --- | --- | --- |
| **O(log⁡n)O(\\log n)O(logn) (Logarithmic Time)** | Halves the problem size each step | **Binary search, balanced trees** |
| --- | --- | --- |
| **O(n)O(n)O(n) (Linear Time)** | Directly proportional to input size | **Array traversal** |
| --- | --- | --- |
| **O(n2)O(n^2)O(n2) (Quadratic Time)** | Nested loops | **Bubble sort, selection sort** |
| --- | --- | --- |
| **O(n!)O(n!)O(n!) (Factorial Time)** | All possible orderings | **Traveling salesman problem** |
| --- | --- | --- |

## **8️⃣ Common Interview Problems & Math Concepts**

| **Problem** | **Related Math Concept** | **Complexity** |
| --- | --- | --- |
| **Binary Search** | Logarithm log⁡n\\log nlogn | O(log⁡n)O(\\log n)O(logn) |
| --- | --- | --- |
| **Bubble Sort** | Arithmetic sum | O(n2)O(n^2)O(n2) |
| --- | --- | --- |
| **Fibonacci Sequence** | Recursion, Golden Ratio | O(2n)O(2^n)O(2n) |
| --- | --- | --- |
| **Generating Permutations** | Factorial n!n!n! | O(n!)O(n!)O(n!) |
| --- | --- | --- |
| **Generating Subsets** | Power set 2n2^n2n | O(2n)O(2^n)O(2n) |
| --- | --- | --- |

## **9️⃣ Key Takeaways**

- **Binary-related problems → O(log⁡n)O(\\log n)O(logn)** (Binary search, balanced trees)
- **Nested loops → O(n2)O(n^2)O(n2)** (Sorting, DP)
- **Exponential growth → O(2n)O(2^n)O(2n)** (Recursion, subset problems)
- **Factorial problems → O(n!)O(n!)O(n!)** (Backtracking, permutations)
- 



​​ **📌 Key Technical Terms for Coding Interviews**

This is a **comprehensive glossary** of common terms used**time complexity, algorithms, and data structures**.

## **1️⃣ Time Complexity Analysis**

| **Term** | **Definition** | **Common Examples** |
| --- | --- | --- |
| **Big-O Notation** | Describe | O(  |
| --- | --- | --- |
| **Constant Time O(1)O(1)O(1)** | The algorithm runs in a fixed number | Array access, Hash |
| --- | --- | --- |
| **Logarithmic Time O(log⁡N)O(\\log N)O(logN)** | The problem size halves each step | Binary search, Balanced BST loo |
| --- | --- | --- |
| **Linear Time O(N)O(N)O(N)** | The algorithm runs in proportion | Looping through an array |
| --- | --- | --- |
| **Linearithmic Time O(Nlog⁡N)O(N \\log N)O(NlogN)** | Combination of linear and logarithmic | Merge sort, Quick sort (avg case) |
| --- | --- | --- |
| **Quadratic Time O(N2)O(N^2)O(N2)** | Algorithms with nested loops | Bubb |
| --- | --- | --- |
| **Exponential Time O(2N)O(2^N)O(2N)** | Growth doubles with | Subset generation, backtracking |
| --- | --- | --- |
| **Factorial Time O(N!)O(N!)O(N!)** | Generates all poss | Generating permutations (TSP, backtracking) |
| --- | --- | --- |

## **2️⃣ Common Algorithmic Concepts**

| **Concept** | **Definition** | **Common Uses** |
| --- | --- | --- |
| **Recursion** | A function calls | DFS, Divide and Conquer, Backtracking |
| --- | --- | --- |
| **Divide and Conquer** | Breaks problem into smaller sub | Merge Sort, Quick Sort, Binary Search |
| --- | --- | --- |
| **Dynamic Programming (DP)** | Solves problems by storing past results to avoid recomputation | Fibonacci, Knapsack Problem |
| --- | --- | --- |
| **Greedy Algorithm** | Makes the best choice at each step without backtracking | Huffman Coding, Kruskal’s Algorithm |
| --- | --- | --- |
| **Backtracking** | Tries all possibilities but prunes invalid paths | N-Queens, Sudoku Solver |
| --- | --- | --- |
| **Bit Manipulation** | Uses binary operations to optimize performance | XOR swap, Bitwise AND/OR |
| --- | --- | --- |

## **3️⃣ Data Structures**

| **Data Structure** | **Definition** | **Time Complexity** |
| --- | --- | --- |
| **Array** | Fixed-size collection of elements | **Access: O(1), Insert/Delete: O(N)** |
| --- | --- | --- |
| **Linked List** | Sequential list where each node points to the next | **Access: O(N), Insert/Delete: O(1)** |
| --- | --- | --- |
| **Stack** | LIFO (Last In, First Out) | **Push/Pop: O(1), Access: O(N)** |
| --- | --- | --- |
| **Queue** | FIFO (First In, First Out) | **Enqueue/Dequeue: O(1), Access: O(N)** |
| --- | --- | --- |
| **Heap (Priority Queue)** | Binary tree where parent nodes have a specific order | **Insert/Delete: O(log N), Find Min/Max: O(1)** |
| --- | --- | --- |
| **Hash Table** | Stores key-value pairs with fast lookups | **Insert/Delete/Access: O(1) avg, O(N) worst** |
| --- | --- | --- |
| **Binary Search Tree (BST)** | A tree where left < root < right | **Search/Insert/Delete: O(log N) avg, O(N) worst** |
| --- | --- | --- |
| **Trie (Prefix Tree)** | Efficient for prefix-based search | **Insert/Search: O(L) (L = word length)** |
| --- | --- | --- |
| **Graph** | Nodes connected by edges | **Adjacency List: O(V+E), Adjacency Matrix: O(V²)** |
| --- | --- | --- |

## **4️⃣ Common Algorithms**

| **Algorithm** | **Category** | **Time Complexity** |
| --- | --- | --- |
| **Binary Search** | Search | **O(log N)** |
| --- | --- | --- |
| **Merge Sort** | Sorting | **O(N log N)** |
| --- | --- | --- |
| **Quick Sort** | Sorting | **O(N log N) avg, O(N²) worst** |
| --- | --- | --- |
| **Dijkstra’s Algorithm** | Shortest Path (Graph) | **O(V + E log V)** |
| --- | --- | --- |
| **Floyd-Warshall Algorithm** | All-Pairs Shortest Paths | **O(V³)** |
| --- | --- | --- |
| **Bellman-Ford Algorithm** | Shortest Path with Negative Weights | **O(VE)** |
| --- | --- | --- |
| **Kruskal’s Algorithm** | Minimum Spanning Tree (MST) | **O(E log V)** |
| --- | --- | --- |
| **Prim’s Algorithm** | Minimum Spanning Tree (MST) | **O(E + V log V)** |
| --- | --- | --- |
| **Floyd’s Cycle Detection** | Detects cycles in linked lists | **O(N)** |
| --- | --- | --- |
| **Topological Sort** | Orders a DAG (Directed Acyclic Graph) | **O(V + E)** |
| --- | --- | --- |

## **5️⃣ Space Complexity**

| **Space Complexity** | **Description** | **Example** |
| --- | --- | --- |
| **O(1)** | Uses constant space | Swapping two variables |
| --- | --- | --- |
| **O(N)** | Space grows linearly with input size | Storing elements in an array |
| --- | --- | --- |
| **O(N²)** | Stores all pairs of elements | Adjacency matrix for graphs |
| --- | --- | --- |
| **O(2^N)** | Stores all subsets | Recursion tree for subset generation |
| --- | --- | --- |
| **O(N!)** | Stores all permutations | Backtracking algorithms |
| --- | --- | --- |

## **6️⃣ Problem-Solving Strategies**

| **Strategy** | **Description** | **Example Problems** |
| --- | --- | --- |
| **Sliding Window** | Moves a fixed-size window across an array | Longest Substring Without Repeating Characters |
| --- | --- | --- |
| **Two Pointers** | Uses two indices moving towards each other | Two Sum (Sorted), Container with Most Water |
| --- | --- | --- |
| **Prefix Sum** | Stores cumulative sums to optimize range queries | Subarray Sum Equals K |
| --- | --- | --- |
| **Binary Lifting** | Optimizes jump operations in trees | LCA (Lowest Common Ancestor) |
| --- | --- | --- |
| **Union-Find (Disjoint Set)** | Tracks connected components | Kruskal’s Algorithm, Cycle Detection |
| --- | --- | --- |

## **7️⃣ Interview Scenarios**

| **Scenario** | **Common Time Complexity** | **Typical Data Structures** |
| --- | --- | --- |
| **Sorting large data** | **O(N log N)** | Merge Sort, Quick Sort |
| --- | --- | --- |
| **Searching in sorted data** | **O(log N)** | Binary Search, BST |
| --- | --- | --- |
| **Finding shortest path** | **O(V + E log V)** | Dijkstra’s Algorithm, Graphs |
| --- | --- | --- |
| **Processing streams of data** | **O(1) - O(log N)** | Heap, Hash Map |
| --- | --- | --- |
| **Checking if a number exists** | **O(1) - O(log N)** | Hash Map, Binary Search |
| --- | --- | --- |
| **Finding top K elements** | **O(K log N)** | Min/Max Heap |
| --- | --- | --- |

## **8️⃣ Complexity-Based Decision Making**

| **Given Constraints NNN** | **Preferred Algorithm** | **Time Complexity** |
| --- | --- | --- |
| N≤109N \\leq 10^9N≤109 | **O(log N)** | Binary Search, Balanced BST |
| --- | --- | --- |
| N≤106N \\leq 10^6N≤106 | **O(N)** | Linear search, DFS, BFS |
| --- | --- | --- |
| N≤105N \\leq 10^5N≤105 | **O(N log N)** | Sorting, Heap operations |
| --- | --- | --- |
| N≤3000N \\leq 3000N≤3000 | **O(N²)** | Brute-force pairwise comparisons |
| --- | --- | --- |
| N≤20N \\leq 20N≤20 | **O(2^N)** | Subset generation, Backtracking |
| --- | --- | --- |
| N≤12N \\leq 12N≤12 | **O(N!)** | Full permutation, NP-hard problems |
| --- | --- | --- |

### **🎯 Key Takeaways**

1. **Big-O notation helps estimate worst-case performance**.
2. **Common algorithms follow specific complexity patterns**:
    - **O(log N) → Binary Search, BST**
    - **O(N log N) → Sorting, Divide & Conquer**
    - **O(N²) → Brute force nested loops**
    - **O(2ⁿ) → Backtracking, Recursion**
    - **O(N!) → Permutations, NP-hard problems**
3. **Data structures matter**: Choose wisely for **efficient lookup, insertion, and traversal**.
4. **Different problem sizes require different algorithm choices**.

🚀 **Mastering these terms will significantly improve your performance in coding interviews!** 🚀


### **1️⃣ 数字进制**

| **术语** | **定义** | **常见应用** |
| --- | --- | --- |
| **十进制（Base 10）** | 使用 0-9 的数字，适合人类使用 | 日常计算 |
| --- | --- | --- |
| **二进制（Base 2）** | 只使用 0 和 1 | 计算机，位运算 |
| --- | --- | --- |
| **十六进制（Base 16）** | 使用 0-9 和 A-F 的数字 | 内存地址，颜色编码 |
| --- | --- | --- |

🔹 **示例：二进制转十进制  
**二进制 1011 → 1×23+0×22+1×21+1×20=8+0+2+1=111 \\times 2^3 + 0 \\times 2^2 + 1 \\times 2^1 + 1 \\times 2^0 = 8 + 0 + 2 + 1 = 111×23+0×22+1×21+1×20=8+0+2+1=11

### **2️⃣ 对数与指数**

| **术语** | **定义** | **常见应用** |
| --- | --- | --- |
| **指数运算** | aba^bab 表示将 aaa 自乘 bbb 次 | 幂计算 |
| --- | --- | --- |
| **对数** | 指数的逆运算，回答“基数需要乘多少次才能得到该数？” | 二分查找，复杂度分析 |
| --- | --- | --- |
| **二进制对数 log⁡2(N)\\log_2(N)log2​(N)** | 衡量 NNN 能被 2 除多少次 | **二分查找 O(log⁡N)O(\\log N)O(logN)**，树的高度 |
| --- | --- | --- |

🔹 **示例：对数的减少  
**log⁡2(8)=3\\log_2(8) = 3log2​(8)=3，因为 23=82^3 = 823=8  
log⁡2(16)=4\\log_2(16) = 4log2​(16)=4，因为 24=162^4 = 1624=16

### **3️⃣ 等差数列**

| **术语** | **定义** | **常见应用** |
| --- | --- | --- |
| **等差数列** | 每一项和前一项的差为常数 | 计数循环，求和计算 |
| --- | --- | --- |
| **等差数列求和公式** | S=(a1+an)×n2S = \\frac{(a_1 + a_n) \\times n}{2}S=2(a1​+an​)×n​ | **嵌套循环复杂度 O(n2)O(n^2)O(n2)** |
| --- | --- | --- |

🔹 **示例：嵌套循环分析**

javascript

for (let i = 0; i < n; i++) {

for (let j = 0; j <= i; j++) {

doSomething();

}

}

**总执行次数**:  
1+2+3+⋯+n=O(n2)1 + 2 + 3 + \\dots + n = O(n^2)1+2+3+⋯+n=O(n2)

### **4️⃣ 等比数列**

| **术语** | **定义** | **常见应用** |
| --- | --- | --- |
| **等比数列** | 每一项是前一项的常数倍 | **递归问题，二叉树** |
| --- | --- | --- |
| **等比数列求和公式** | S=a1×1−rn1−rS = a_1 \\times \\frac{1 - r^n}{1 - r}S=a1​×1−r1−rn​ | **完美二叉树节点数 O(log⁡N)O(\\log N)O(logN)** |
| --- | --- | --- |

🔹 **示例：完美二叉树**

python-repl

第 0 层：1

第 1 层：2

第 2 层：4

第 3 层：8

...

总节点数：1 + 2 + 4 + ... + 2^h = 2^{h+1} - 1

**高度**: O(log⁡N)O(\\log N)O(logN)

### **5️⃣ 模运算**

| **术语** | **定义** | **常见应用** |
| --- | --- | --- |
| **模（Mod）** | amod  ba \\mod bamodb 是 aaa 除以 bbb 后的余数 | **循环数组，哈希函数，加密** |
| --- | --- | --- |
| **模的分配律** | (a+b)mod  c=\[(amod  c)+(bmod  c)\]mod  c(a + b) \\mod c = \[(a \\mod c) + (b \\mod c)\] \\mod c(a+b)modc=\[(amodc)+(bmodc)\]modc | **大数运算优化** |
| --- | --- | --- |

🔹 **示例：时钟算术**

javascript

15 % 12 = 3 // 15小时制时间转换为 3 PM

🔹 **示例：使用模进行质数检查**

javascript

function isPrime(n) {

if (n < 2) return false;

for (let i = 2; i \* i <= n; i++) {

if (n % i === 0) return false;

}

return true;

}

### **6️⃣ 组合数学（计数）**

| **术语** | **定义** | **常见应用** |
| --- | --- | --- |
| **阶乘 n!n!n!** | n!=n×(n−1)×⋯×1n! = n \\times (n-1) \\times \\dots \\times 1n!=n×(n−1)×⋯×1 | **排列 O(n!)O(n!)O(n!)** |
| --- | --- | --- |
| **排列** | 元素的有序排列 | **生成所有排列** |
| --- | --- | --- |
| **组合** | 元素的无序选择 | **选择子集** |
| --- | --- | --- |
| **子集计算** | 2n2^n2n 是一个包含 nnn 个元素的集合的所有子集 | **子集生成 O(2n)O(2^n)O(2n)** |
| --- | --- | --- |

🔹 **示例：阶乘计算**

javascript

function factorial(n) {

return n === 1 ? 1 : n \* factorial(n - 1);

}

console.log(factorial(5)); // 输出 120

### **7️⃣ 复杂度分析（大 O 记法）**

| **术语** | **定义** | **常见应用** |
| --- | --- | --- |
| **大 O 记法** | 表示最坏情况下的时间复杂度 | 算法分析 |
| --- | --- | --- |
| **O(1)** (常数时间) | 固定时间操作 | **哈希表查找** |
| --- | --- | --- |
| **O(\\log N)** (对数时间) | 每步将问题规模减半 | **二分查找，平衡树** |
| --- | --- | --- |
| **O(N)** (线性时间) | 与输入规模成正比 | **数组遍历** |
| --- | --- | --- |
| **O(N^2)** (平方时间) | 嵌套循环 | **冒泡排序，选择排序** |
| --- | --- | --- |
| **O(2^N)** (指数时间) | 增长速度翻倍 | **子集生成，回溯** |
| --- | --- | --- |
| **O(N!)** (阶乘时间) | 所有可能的排列 | **旅行商问题** |
| --- | --- | --- |

### **8️⃣ 常见面试问题与数学概念**

| **问题** | **相关数学概念** | **复杂度** |
| --- | --- | --- |
| **二分查找** | 对数 log⁡N\\log NlogN | O(log⁡N)O(\\log N)O(logN) |
| --- | --- | --- |
| **冒泡排序** | 等差数列求和 | O(N2)O(N^2)O(N2) |
| --- | --- | --- |
| **斐波那契数列** | 递归，黄金比例 | O(2n)O(2^n)O(2n) |
| --- | --- | --- |
| **生成排列** | 阶乘 n!n!n! | O(n!)O(n!)O(n!) |
| --- | --- | --- |
| **生成子集** | 幂集 2n2^n2n | O(2n)O(2^n)O(2n) |
| --- | --- | --- |

### **9️⃣ 关键总结**

1. **与二进制相关的问题 → O(\\log N)**（如二分查找，平衡树）
2. **嵌套循环 → O(N^2)**（如排序，动态规划）
3. **指数增长 → O(2^N)**（如递归，子集问题）
4. **阶乘问题 → O(N!)**（如回溯，排列问题）
