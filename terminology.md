# Key Math Concepts for Technical Interviews

## 1\. Number Bases

\- Base 10 (Decimal): Uses digits 0-9, common for everyday calculations.

\- Base 2 (Binary): Uses only 0 and 1, important for computers and bitwise operations.

\- Base 16 (Hexadecimal): Uses 0-9 and A-F, used in memory addresses and color codes.

## Example: Binary to Decimal Conversion

\- Binary 1011 -> 1 \* 2^3 + 0 \* 2^2 + 1 \* 2^1 + 1 \* 2^0 = 8 + 0 + 2 + 1 = 11

## 2\. Logarithms & Exponents

\- Exponentiation: a^b means multiplying a by itself b times.

\- Logarithm: Inverse of exponentiation, useful in binary search and complexity analysis.

\- Binary Log (log_2 n): Measures how many times n can be divided by 2.

## Example: Logarithmic Reduction

\- log_2(8) = 3 because 2^3 = 8

\- log_2(16) = 4 because 2^4 = 16

## 3\. Arithmetic Sequence

\- Arithmetic Sequence: A sequence with a constant difference between terms.

\- Arithmetic Sum Formula: S = (a1 + an) \* n / 2

\- Nested loop complexity O(n^2).

## 4\. Geometric Sequence

\- Geometric Sequence: A sequence where each term is multiplied by a constant ratio.

\- Geometric Sum Formula: S = a1 \* (1 - r^n) / (1 - r)

\- Perfect binary tree node count O(log n).

## Example: Perfect Binary Tree

\- Total nodes: 1 + 2 + 4 + ... + 2^h = 2^(h+1) - 1

\- Height: O(log n)

## 5\. Modular Arithmetic

\- Modulo (Mod): a mod b is the remainder when a is divided by b.

\- Mod Distributive Property: (a + b) mod c = \[(a mod c) + (b mod c)\] mod c.

## Example: Clock Arithmetic

\- 15 % 12 = 3 // 15-hour clock time converts to 3 PM

## 6\. Combinatorics (Counting)

\- Factorial (n!): n! = n \* (n - 1) \* ... \* 1.

\- Permutation: Ordered arrangement of elements.

\- Combination: Unordered selection of elements.

\- Subset Calculation: 2^n total subsets of a set with n elements.

## Example: Factorial Calculation

\- factorial(5) = 120

## 7\. Complexity Analysis (Big-O Notation)

\- O(1) (Constant Time): Fixed-time operation (e.g., Hash table lookup).

\- O(log n) (Logarithmic Time): Halves the problem size each step (e.g., Binary search).

\- O(n) (Linear Time): Directly proportional to input size (e.g., Array traversal).

\- O(n^2) (Quadratic Time): Nested loops (e.g., Bubble sort).

\- O(n!) (Factorial Time): All possible orderings (e.g., Traveling salesman problem).

## 8\. Common Interview Problems & Math Concepts

\- Binary Search -> Logarithm log n -> O(log n)

\- Bubble Sort -> Arithmetic sum -> O(n^2)

\- Fibonacci Sequence -> Recursion -> O(2^n)

\- Generating Permutations -> Factorial n! -> O(n!)

\- Generating Subsets -> Power set 2^n -> O(2^n)

## 9\. Key Takeaways

\- Binary-related problems -> O(log n) (Binary search, balanced trees)

\- Nested loops -> O(n^2) (Sorting, DP)

\- Exponential growth -> O(2^n) (Recursion, subset problems)

\- Factorial problems -> O(n!) (Backtracking, permutations)
