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

这类题可以归纳为求一个数组中所有出现次数超过n/k的元素，最简单的做法就是哈希法统计所有元素的出现次数然后遍历map来查询超过n/k次的元素；如果想要在线性时间内使用常数级的空间那么必须依赖于摩尔投票法:     

如果至多选一个代表，那他的票数至少要超过一半（⌊ 1/2 ⌋）的票数；      

如果至多选两个代表，那他们的票数至少要超过 ⌊ 1/3 ⌋ 的票数；   

如果至多选m个代表，那他们的票数至少要超过 ⌊ 1/(m+1) ⌋ 的票数。         

摩尔投票法本质上就是宾果消消乐游戏，每次消除3个不同的数。由于数组长度为n，因此消消乐最多进行[n/3]次。因此，我们想要的答案（超过[n/3]的数字）一定没有被消除完，一定存在最后活下来的两个数当中。 但是，存活的两个数不一定都是想要的真正的答案，最后再遍历确认一下这两个数是不是答案即可。    

```code
var majorityElement = function(nums) {
let candidate1 = null;
let candidate2 = null;
let count1 = 0
let count2 = 0;
for(let i of nums){
    if(candidate1 == i){
        count1++;
    }
    else if(candidate2 == i){
        count2++;
    }
    else if(count1==0){
        candidate1 = i;
        count1 =1;
    }
    else if(count2==0){
        candidate2 = i;
        count2=1;
    }
    else{
        count1--;
        count2--;
    }
}
count1 =0;
count2 =0;
for (let num of nums) {
    if (num === candidate1) count1++;
    else if (num === candidate2) count2++;
}
let result = [];
const n = nums.length;
if (count1 > Math.floor(n / 3)) result.push(candidate1);
if (count2 > Math.floor(n / 3)) result.push(candidate2);
return result;
};
```
