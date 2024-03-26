在此之前需要知道拓扑排序：    
https://www.bilibili.com/video/BV1HL411E7TE/?spm_id_from=333.337.search-card.all.click&vd_source=278d7770421c9ec6698a7d3fd771108a

<img width="808" alt="截屏2024-03-26 19 03 28" src="https://github.com/xkong-study/gucheng_algorithm/assets/100473178/1fa7c7b8-5008-4bb0-ab87-0a2b121c44f7">

模版         
```code
function topologicalSort(numNodes, edges) {
    const indegree = new Array(numNodes).fill(0);
    const adjList = new Map();
    const order = [];
    for (let i = 0; i < numNodes; i++) {
        adjList.set(i, []);
    }
    for (let [start, end] of edges) {
        adjList.get(start).push(end);
        indegree[end]++;
    }
    const queue = [];
    for (let i = 0; i < numNodes; i++) {
        if (indegree[i] === 0) {
            queue.push(i);
        }
    }
    while (queue.length) {
        const node = queue.shift();
        order.push(node);

        // Decrease indegree of neighboring nodes
        for (let neighbor of adjList.get(node)) {
            indegree[neighbor]--;
            if (indegree[neighbor] === 0) {
                queue.push(neighbor);
            }
        }
    }
    if (order.length !== numNodes) {
        throw new Error("There is a cycle in the graph!");
    }
    return order;
}
```
![3061711482096_ pic_hd](https://github.com/xkong-study/gucheng_algorithm/assets/100473178/b81e9165-3234-4f96-b929-8dad504a4144)
