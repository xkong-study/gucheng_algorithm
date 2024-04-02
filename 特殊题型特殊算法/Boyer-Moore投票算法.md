https://cloud.tencent.com/developer/article/1600607  
LeetCode 169. 多数元素[1]  

详细图解     
以 [2,2,1,3,1,2,2] 为例。        

遍历数组第一个元素 2 时，因 major 空缺，所以赋值 major = 2，且票数 count = 1：           
![image](https://github.com/xkong-study/gucheng_algorithm/assets/100473178/dc650aac-4911-4e9d-bd16-ecfc8db5d658)

```code
function majorityElement(nums) {
    let count = 0;
    let candidate = null;

    for (let num of nums) {
        if (count === 0) {
            candidate = num;
        }
        count += (num === candidate) ? 1 : -1;
    }

    // candidate 此时为多数元素
    return candidate;
}

```

推荐大家可以再做做这道题：LeetCode 229. 求众数 II[2]   
