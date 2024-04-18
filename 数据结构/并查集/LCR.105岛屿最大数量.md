```code
var maxAreaOfIsland = function(grid) {
    let width = grid[0].length;
    let height = grid.length;
    let dsu = new DSU(width * height);
    let max = 0;
    const getIndex = (i, j) => i * width + j;
    for(let i = 0; i < height; i++){
        for(let j = 0; j < width; j++){
            if(grid[i][j] === 1){
                grid[i][j] = 0;
                let currentArea =1;
                if(i+1 < height && grid[i+1][j] === 1) currentArea = dsu.union(getIndex(i, j), getIndex(i+1, j));
                if(i-1 >= 0 && grid[i-1][j] === 1) currentArea = dsu.union(getIndex(i, j), getIndex(i-1, j));
                if(j+1 < width && grid[i][j+1] === 1) currentArea = dsu.union(getIndex(i, j), getIndex(i, j+1));
                if(j-1 >= 0 && grid[i][j-1] === 1) currentArea = dsu.union(getIndex(i, j), getIndex(i, j-1));
                max = Math.max(max, currentArea);
            }
        }
    }
    return max;
};

function DSU(n){
    this.parent = new Array(n);
    this.rank = new Array(n);
    this.area = new Array(n).fill(1);
    
    for(let i = 0; i < n; i++){
        this.parent[i] = i;
        this.rank[i] = 0;
    }
}

DSU.prototype.find = function(x) {
    if (this.parent[x] !== x) {
        this.parent[x] = this.find(this.parent[x]);
    }
    return this.parent[x];
};

DSU.prototype.union = function(x, y) {
    let rootX = this.find(x);
    let rootY = this.find(y);

    if (rootX !== rootY) {
        if (this.rank[rootX] < this.rank[rootY]) {
            this.parent[rootX] = rootY;
            this.area[rootY] += this.area[rootX];
        } else if (this.rank[rootX] > this.rank[rootY]) {
            this.parent[rootY] = rootX;
            this.area[rootX] += this.area[rootY];
        } else {
            this.parent[rootY] = rootX;
            this.rank[rootX]++;
            this.area[rootX] += this.area[rootY];
        }
    }
    
    return this.area[this.find(x)];
};

```
