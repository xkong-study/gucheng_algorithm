二维数组转换成BFS的逻辑    
在这个场景中，二维数组已经自然地映射到了一个图的结构，其中数组的每个元素可以看作一个节点，节点之间的边由方向数组dirs定义。BFS通过队列来探索所有可能的路径，直到找到终点或确定没有路径存在。      

这段代码利用了BFS算法的核心思想，即逐层探索，每次都从当前节点出发探索所有未访问过的邻居节点，这些邻居节点又成为下一轮探索的起点，直到找到目标或遍历完所有节点。    

二维转成bfs的模版。      

```code
// BFS模板：用于在二维数组中搜索从起点到终点的路径
function bfsSearch(maze, start, destination) {
    // 如果迷宫为空，则直接返回false
    if (maze.length === 0 || maze[0].length === 0) return false;

    // 定义四个可能的移动方向（上、下、左、右）
    const directions = [[-1, 0], [1, 0], [0, -1], [0, 1]];

    // 初始化访问数组，用于记录节点是否被访问过
    let visited = Array(maze.length).fill(false).map(() => Array(maze[0].length).fill(false));

    // 初始化队列，并将起点加入队列
    let queue = [start];
    visited[start[0]][start[1]] = true; // 标记起点为已访问

    // 开始进行BFS遍历
    while (queue.length > 0) {
        let [x, y] = queue.shift(); // 从队列中取出当前节点

        // 如果当前节点是终点，则返回true
        if (x === destination[0] && y === destination[1]) return true;

        // 遍历所有可能的移动方向
        for (let [dx, dy] of directions) {
            let newX = x + dx, newY = y + dy;

            // 检查新位置是否有效（在迷宫内、不是墙壁、未被访问过）
            if (newX >= 0 && newX < maze.length && newY >= 0 && newY < maze[0].length && maze[newX][newY] === 0 && !visited[newX][newY]) {
                queue.push([newX, newY]); // 将新位置加入队列
                visited[newX][newY] = true; // 标记新位置为已访问
            }
        }
    }

    // 如果遍历完所有节点都没有找到终点，则返回false
    return false;
}

```

