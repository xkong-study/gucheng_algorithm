这两道题的区别就在于，下一个更大元素II有重复元素，所以stack应该存索引。
```code
var nextGreaterElements = function(nums) {
let stack = []
let res = new Array(nums.length).fill(-1);
for(let i=0;i<nums.length*2;i++){
    while(nums[i%nums.length]>nums[stack[stack.length-1]]){
        let temp = stack.pop();
        res[temp] = nums[i%nums.length];
    }
    stack.push(i%nums.length);
}
return res;
};

```
