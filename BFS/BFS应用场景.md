1.可以在tree。    
2.可以在graph。     
3.可以在二维数组。     
4.求最短路径。    


有向图=》bfs（拓扑排序，先找关系关系找到了找权重，然后bfs遍历去掉权重是0的节点，一点点减去权重减去节点，节点放入order数组）课程表和课程表II（比较order是否节点完整），都是这样写的。         

树=》bfs都是比较基础的二叉树层序遍历题。      

二维数组=〉bfs，这个都是单词搜索啊迷宫，迷宫II这种题，这种题不要忘记标记访问过的地方提高速度。比如单词搜索这种线性的就是谁先到终点谁快，不需要标记走了多少步不像迷宫II每一步的步数都不一样所以不可以用线性表示快慢要多一个标记计步数。      


  
深度优先搜索 (DFS)：    

当您需要找到所有可能的解，或者需要找到一条路径时，DFS是一个不错的选择。      
DFS通常用于解决能够构成树形结构的问题，例如遍历树、寻找所有可能的路径、解决回溯问题等。       
DFS使用栈来存储待访问的节点，因此它的空间复杂度相对较低，但是由于可能会穷尽所有可能的路径，因此有时候可能会陷入无限循环中。      
DFS不保证找到最短路径，但在某些情况下可以通过额外的优化来实现这一点。        

广度优先搜索 (BFS)：            
     
当您需要找到最短路径时，BFS通常是一个更好的选择，因为它从距离起点最近的节点开始搜索，能够保证找到最短路径。          
BFS适用于解决无权图的最短路径问题、网络爬虫、最短路径问题等。        
BFS使用队列来存储待访问的节点，因此它的空间复杂度相对较高，但是由于它能够保证找到最短路径，因此在某些情况下这个额外的开销是值得的。         
BFS的时间复杂度通常比DFS高，但是它的应用场景更加广泛。        
