# 📌 Longest Increasing Subsequence (LIS) - Interview Explanation

## 🔹 1. Problem Statement

We are given an integer array \`nums\`, and we need to find the length of the longest increasing subsequence (LIS).

💡 Example:

Input: nums = \[50, 3, 10, 7, 40, 80\]  
Output: 4  
Explanation: LIS = \[3, 7, 40, 80\]  

## 🔹 2. Approach 1: Brute-Force DFS (O(2ⁿ))

💡 Key Idea: Try all possible subsequences using DFS (Depth-First Search).

💻 Code:

function lengthOfLIS(nums) {  
function dfs(index, prevIndex) {  
if (index >= nums.length) return 0;  
let skip = dfs(index + 1, prevIndex);  
let pick = 0;  
if (prevIndex === -1 || nums\[index\] > nums\[prevIndex\]) {  
pick = 1 + dfs(index + 1, index);  
}  
return Math.max(skip, pick);  
}  
return dfs(0, -1);  
}  

## 🔹 3. Approach 2: DFS + Memoization (O(n²))

💡 Key Idea: Use Memoization (Caching) to avoid recomputation.

💻 Code:

function lengthOfLIS(nums) {  
let memo = new Map();  
function dfs(index, prevIndex) {  
let key = \`${index},${prevIndex}\`;  
if (memo.has(key)) return memo.get(key);  
if (index >= nums.length) return 0;  
let skip = dfs(index + 1, prevIndex);  
let pick = 0;  
if (prevIndex === -1 || nums\[index\] > nums\[prevIndex\]) {  
pick = 1 + dfs(index + 1, index);  
}  
let result = Math.max(skip, pick);  
memo.set(key, result);  
return result;  
}  
return dfs(0, -1);  
}  

## 🔹 4. Approach 3: Classic DP (O(n²))

💡 Key Idea: Define \`dp\[i\]\` as the length of the LIS ending at index \`i\`.

💻 Code:

function lengthOfLIS(nums) {  
let n = nums.length;  
let dp = new Array(n).fill(1);  
let maxLen = 1;  
for (let i = 1; i < n; i++) {  
for (let j = 0; j < i; j++) {  
if (nums\[j\] < nums\[i\]) {  
dp\[i\] = Math.max(dp\[i\], dp\[j\] + 1);  
}  
}  
maxLen = Math.max(maxLen, dp\[i\]);  
}  
return maxLen;  
}  

## 🔹 5. Approach 4: DP + Binary Search (O(n log n))

💡 Key Idea: Use Greedy + Binary Search to maintain an increasing subsequence.

💻 Code:

function lengthOfLIS(nums) {  
let sub = \[\];  
for (let num of nums) {  
let left = 0, right = sub.length;  
while (left < right) {  
let mid = Math.floor((left + right) / 2);  
if (sub\[mid\] >= num) {  
right = mid;  
} else {  
left = mid + 1;  
}  
}  
if (left < sub.length) {  
sub\[left\] = num;  
} else {  
sub.push(num);  
}  
}  
return sub.length;  
}  

## 🔹 6. Complexity Comparison

| Approach | Time Complexity | Space Complexity | Key Idea |
| --- | --- | --- | --- |
| Brute-Force DFS | O(2ⁿ) | O(n) | Try all subsequences |
| DFS + Memoization | O(n²) | O(n²) | Store computed results |
| DP (O(n²)) | O(n²) | O(n) | Use \`dp\[i\]\` for LIS ending at \`i\` |
| Greedy + Binary Search (O(n log n)) | O(n log n) | O(n) | Use \`sub\[\]\` to track LIS |

## 🔹 7. Summary

1\. \*\*Brute Force DFS (O(2ⁿ))\*\* → Tries all subsequences, impractical.

2\. \*\*DFS + Memoization (O(n²))\*\* → Optimizes DFS with caching.

3\. \*\*Classic DP (O(n²))\*\* → Uses \`dp\[i\]\`, easy to understand.

4\. \*\*Greedy + Binary Search (O(n log n))\*\* → Fastest, but harder to implement.

## 🚀 Final Thought

The optimal solution (O(n log n)) combines greedy and binary search, maintaining a dynamic sequence of LIS candidates. However, understanding O(n²) DP is crucial before implementing it.

## 📌 What If the Interviewer Asks

1\. \*\*Can you reconstruct the actual LIS?\*\* → Need to track indices while building \`sub\` (extra storage needed).

2\. \*\*Can we do better than O(n log n)?\*\* → No, this is the best known complexity for LIS.

3\. \*\*What if all numbers are the same?\*\* → LIS length is 1.
