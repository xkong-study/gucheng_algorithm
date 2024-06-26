BFS:迷宫，课程表，单词接龙   =》 最短路径 + 逐层扩展 + 避免重复访问（level+queue）          

DFS:解数独，n皇后 =〉 是否可能存在解（dfs返回true/false） 解是什么（dfs不返回值） + 约束条件多(level+是否可以选择的节点)                  


总结起来，广度优先搜索（BFS）通常用于寻找最短路径或最优解的问题，因为它能够有效地探索多个可能性并按层次逐步扩展搜索范围，以确保找到的解决方案是最优的。BFS还能够避免重复访问相同的节点，提高搜索效率。       

而深度优先搜索（DFS）则通常用于需要穷尽所有可能性的问题，尤其是在需要回溯和处理大量约束条件的情况下。DFS在搜索过程中通常只会得到一种可能的解法，或者用于判断是否存在解决方案，而不会得到最优解。     

因此，BFS适用于需要找到最短路径或最优解的问题，而DFS适用于需要穷尽所有可能性或判断解决方案是否存在的问题。在问题的解空间比较大或者有很多约束条件时，DFS可能会更合适，因为它的搜索策略更加灵活，可以逐步探索所有可能性。      

## 重点
BFS:  
level: 用来记录最短/最快        
queue：运动四个方向，26个字母     
去重： width*row + col => visited    

DFS:    
level: col/row      
是否可以选择的子节点： 1-9的数值， 是不是皇冠     
约束条件多：写用来约束的函数      

BFS的答案是通过level获取的，DFS的答案是通过for循环判断是否可以选择作为子节点获取的           

![3631714155478_ pic_hd](https://github.com/xkong-study/gucheng_algorithm/assets/100473178/2a7f555e-9c56-45cb-add2-0009b3ecbf29)

