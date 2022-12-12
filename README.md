1)**BFS**
graph={
    '1':['2','10'],
    '2':['3','8'],
    '3':['4'],
    '4':['5','6','7'],
    '5':[],
    '6':[],
    '7':[], 
    '8':['9'], 
    '9':[],
    '10':[]    
}
visited=[]
queue=[]
def bfs(visited,graph,node):
    visited.append(node)
    queue.append(node)
    while queue:
        m=queue.pop(0)
        print(m,end=' ')
        for neighbour in graph[m]:
            if neighbour not in visited:
                visited.append(neighbour)
                queue.append(neighbour)
print("following is the breadth first search")
bfs(visited,graph,'1')
         
         
  2)**DFS**       
        graph={
    '5':['3','7'],
    '3':['2','4'],
    '7':['6'],
    '6':[],
    '2':['1'],
    '1':[],
    '4':['8'], 
    '8':[]    
}
visited=set()
def dfs(visited,graph,node):
    if node not in visited:
        print(node)
        visited.add(node)
        for neighbour in graph[node]:
            dfs(visited,graph,neighbour)
print("following is the depth first search")
dfs(visited,graph,'5')
          
