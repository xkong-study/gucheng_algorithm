```
function intervalDP(arr, operationType) {
    const n = arr.length;
    
    // 1️⃣ 初始化 DP 数组
    const dp = Array.from({ length: n }, () => Array(n).fill(Infinity));

    // 2️⃣ 计算前缀和（如果问题涉及区间和）
    const prefixSum = new Array(n + 1).fill(0);
    for (let i = 1; i <= n; i++) {
        prefixSum[i] = prefixSum[i - 1] + arr[i - 1];
    }

    // 3️⃣ Base Case（单个元素的区间）
    for (let i = 0; i < n; i++) {
        if (operationType === "merge") {
            dp[i][i] = 0;  // **合并问题**：合并单个元素代价为 0
        } else if (operationType === "game") {
            dp[i][i] = arr[i]; // **博弈问题**：只有一个硬币时，玩家只能拿这个硬币
        } else if (operationType === "palindrome") {
            dp[i][i] = 0; // **回文分割问题**：单字符不需要切割
        }
    }

    // 4️⃣ 递推计算 DP 表，从小区间到大区间
    for (let length = 2; length <= n; length++) {  // 区间长度从 2 到 n
        for (let l = 0; l + length - 1 < n; l++) { // 区间左端点
            let r = l + length - 1; // 计算右端点

            if (operationType === "merge") {
                // **合并代价最小**
                for (let k = l; k < r; k++) {
                    dp[l][r] = Math.min(dp[l][r], dp[l][k] + dp[k+1][r] + (prefixSum[r+1] - prefixSum[l]));
                }
            } 
            else if (operationType === "game") {
                // **游戏最优策略**
                dp[l][r] = prefixSum[r+1] - prefixSum[l] - Math.min(dp[l+1][r], dp[l][r-1]);
            } 
            else if (operationType === "palindrome") {
                // **最小回文分割**
                for (let k = l; k < r; k++) {
                    dp[l][r] = Math.min(dp[l][r], dp[l][k] + dp[k+1][r] + 1);
                }
            }
        }
    }
    
    return dp[0][n-1]; // 返回最终答案
}
```
