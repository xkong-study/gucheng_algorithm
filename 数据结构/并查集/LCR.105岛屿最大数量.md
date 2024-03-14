```code
var maxAreaOfIsland = function(grid) {
    let maxArea = 0;
    let width = grid[0].length;
    let height = grid.length;
    let dsu = new DSU(width*height);
    let direction = [[-1,0],[1,0],[0,1],[0,-1]];
    for(let i = 0; i < height; i++){
        for(let j = 0; j < width; j++){
            if(grid[i][j] == 1){
                let area = 0;
                const Original = i*width+j;
                for(let [x, y] of direction){
                    let newX = i + x;
                    let newY = j + y;
                    if(newX < 0 || newY < 0 || newX >= height || newY >= width) continue;
                    const New = newX * width + newY;
                    if(grid[newX][newY] === 1 && dsu.find(New) !== dsu.find(Original)){
                        dsu.union(Original, New);
                    }
                }
                area = dsu.countSize(Original, width);
                maxArea = Math.max(maxArea, area);
            }
        }
    }
    return maxArea;
};

var DSU = function(n){
    this.parent = [];
    for(let i = 0; i < n; i++){
        this.parent[i] = i;
    }
}

DSU.prototype.find = function(x){
    if(this.parent[x] !== x){
        this.parent[x] = this.find(this.parent[x]);
    }
    return this.parent[x];
}

DSU.prototype.union = function(x, y){
    let rootA = this.find(x);
    let rootB = this.find(y);
    if(rootA !== rootB){
        this.parent[rootB] = rootA;
    }
}

DSU.prototype.countSize = function(x, width) {
    let root = this.find(x);
    let size = 0;
    for(let i = 0; i < this.parent.length; i++) {
        if(this.find(i) === root) size++;
    }
    return size;
}

```
