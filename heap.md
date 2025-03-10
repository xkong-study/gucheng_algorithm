## **Heap Fundamentals (堆基础)**

### **Approach**

- A **heap** is a specialized binary tree-based data structure used to maintain the **maximum or minimum element** efficiently.
- A **min-heap** allows **quick access to the smallest element**, while a **max-heap** gives **quick access to the largest element**.
- **Insertion and deletion** operations in a heap take **O(log N) time**, and retrieving the top element is **O(1)**.
- **Heapify operations** can construct a heap from an array in **O(N) time**.

### **Interview Phrases**

- "Since we need to maintain the largest (or smallest) element efficiently, a heap is an optimal choice."
- "A min-heap is useful when we need to retrieve the smallest element repeatedly."
- "A max-heap is ideal when tracking the K largest elements dynamically."
- "Heap operations such as insertion and deletion take logarithmic time, making it efficient for priority-based retrieval."

## **Top K Elements (前 K 个元素)**

### **Approach**

- Use a **min-heap of size K** to store the top **K largest elements** efficiently.
- Use a **max-heap** when retrieving the **K smallest elements**.
- If the data is static, sorting is an alternative, but for streaming data, heaps are more efficient.

### **Interview Phrases**

- "Since we only need to keep track of K elements, I will use a min-heap of size K."
- "By maintaining a heap of size K, we ensure an efficient O(N log K) solution."
- "Sorting would take O(N log N), but using a heap allows us to optimize to O(N log K)."
- "For dynamic streaming data, heaps are better than sorting since we can process elements one at a time."

## **K Closest Points (K 最近点)**

### **Approach**

- Use a **max-heap** of size K to store the K closest points to the origin.
- Push elements into the heap based on their **Euclidean distance**.
- Remove elements when the heap exceeds size K.

### **Interview Phrases**

- "Since we need the K closest points, I will use a max-heap of size K."
- "I will store the points in a max-heap based on their squared Euclidean distance."
- "If the heap exceeds K elements, I will remove the farthest point to keep only the closest K."

## **Merge K Sorted Lists (合并 K 个排序列表)**

### **Approach**

- Use a **min-heap** to efficiently merge multiple sorted lists.
- Push the first element of each list into the heap.
- Extract the minimum element and insert its next element from the same list.
- Repeat until all elements are merged.

### **Interview Phrases**

- "A min-heap allows us to efficiently merge multiple sorted lists in O(N log K) time."
- "Since we are always extracting the smallest element, a priority queue is the best choice."
- "By pushing the first element of each list into the heap, we ensure that we always have access to the smallest element across all lists."

## **Kth Largest Element in an Array (数组中的第 K 大元素)**

### **Approach**

- Use a **min-heap of size K** to track the K largest elements.
- Iterate through the array and push each element into the heap.
- If the heap size exceeds K, remove the smallest element.

### **Interview Phrases**

- "I will maintain a min-heap of size K to efficiently track the K largest elements."
- "Since we only need the K largest elements, keeping a heap of size K ensures O(N log K) complexity."
- "Using a max-heap would require storing all elements, which is unnecessary."

## **Kth Smallest Element in a Sorted Matrix (排序矩阵中的第 K 小元素)**

### **Approach**

- Use a **min-heap** to extract elements row by row.
- Push the first element of each row into the heap.
- Extract the smallest element K times to find the Kth smallest.

### **Interview Phrases**

- "Since the matrix rows and columns are sorted, a heap allows efficient extraction of the Kth smallest element."
- "I will push the first element of each row into a min-heap and extract elements sequentially."
- "This approach ensures an O(K log N) time complexity, which is optimal given the constraints."

## **Reorganize String (重新组织字符串)**

### **Approach**

- Use a **max-heap** to store character frequencies.
- Always extract the most frequent character first to avoid consecutive duplicates.
- Use a queue to keep track of the last used character to ensure valid placement.

### **Interview Phrases**

- "A max-heap helps track the most frequent character while ensuring valid placement."
- "By always extracting the character with the highest count, we maximize spacing between duplicates."
- "If at any point the heap is empty before all characters are placed, it means the task is impossible."

## **Ugly Number (丑陋数)**

### **Approach**

- Use a **min-heap** to generate ugly numbers in increasing order.
- Start with 1 and repeatedly multiply by **2, 3, and 5** while maintaining uniqueness using a hash set.

### **Interview Phrases**

- "I will use a min-heap to generate ugly numbers in sorted order."
- "To avoid duplicates, I will store numbers in a set before pushing them into the heap."
- "This ensures that we always get the next smallest ugly number efficiently."

## **Median of Data Stream (数据流的中位数)**

### **Approach**

- Use **two heaps**:
  - A **max-heap** to store the smaller half of the numbers.
  - A **min-heap** to store the larger half.
- The **median** is the root of the max-heap (odd number of elements) or the average of both heaps' roots (even number of elements).
- Ensure both heaps stay balanced (difference in size is at most 1).

### **Interview Phrases**

- "I will use two heaps: a max-heap for the lower half and a min-heap for the upper half."
- "The max-heap stores the smaller numbers, and the min-heap stores the larger numbers."
- "The median is always at the root of the max-heap or the average of both heap roots if the total count is even."
- "By balancing the two heaps dynamically, we can efficiently compute the median in O(log N) time per insertion."
