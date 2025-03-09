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
