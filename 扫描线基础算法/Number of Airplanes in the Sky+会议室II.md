什么是扫描线?    
拿数飞机举例    
思路一，暴力扫描    
遍历每个时刻，检测每个时刻有多少个飞机    
思路二，扫描线!   
不需要检测每一时刻，只需要检测起点或者终点的位置!    

![截屏2024-02-05 15.21.56.png](https://img.xwyue.com/i/2024/02/05/65c0fd1abbb15.png)

描述     
给出飞机的起飞和降落时间的列表，用序列 interval 表示. 请计算出天上同时最多有多少架飞机？   

如果多架飞机降落和起飞在同一时刻，我们认为降落有优先权。     

样例      
样例 1:     
输入: [(1, 10), (2, 3), (5, 8), (4, 7)]   
输出: 3    
解释:    
第一架飞机在1时刻起飞, 10时刻降落.    
第二架飞机在2时刻起飞, 3时刻降落.    
第三架飞机在5时刻起飞, 8时刻降落.   
第四架飞机在4时刻起飞, 7时刻降落.   
在5时刻到6时刻之间, 天空中有三架飞机.  

```code
var minMeetingRooms = function(intervals) {
let map = new Map();
let sum = 0;
let max = 1;
for(let i of intervals){
    map.has(i[0])?map.set(i[0],map.get(i[0])+1):map.set(i[0],1);
    map.has(i[1])?map.set(i[1],map.get(i[1])-1):map.set(i[1],-1);
}
let indexArr = Array.from(map.keys()).sort((a, b) => a - b);
for(let i=0;i<indexArr.length;i++){
    max = Math.max(max,sum);
    sum+=map.get(indexArr[i]);
}
return max;
};
```
