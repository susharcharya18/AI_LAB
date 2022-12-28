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
    
    3)
    # Recursive Python function to solve the tower of hanoi
def TowerOfHanoi(n , source, destination, auxiliary):
    if n==1:
        print ("Move disk 1 from source",source,"to destination",destination)
        return
    TowerOfHanoi(n-1, source, auxiliary, destination)
    print ("Move disk",n,"from source",source,"to destination",destination)
    TowerOfHanoi(n-1, auxiliary, destination, source)
         
    # Driver code
    n = 3
    TowerOfHanoi(n,'A','B','C')
    # A, C, B are the name of rods
 output:
 Move disk 1 from source A to destination B
Move disk 2 from source A to destination C
Move disk 1 from source B to destination C
Move disk 3 from source A to destination B
Move disk 1 from source C to destination A
Move disk 2 from source C to destination B
Move disk 1 from source A to destination B

4)
     # This function is used to initialize the 
     # dictionary elements with a default value.
from collections import defaultdict
  
     # jug1 and jug2 contain the value 
     # for max capacity in respective jugs 
     # and aim is the amount of water to be measured. 
jug1, jug2, aim = 4, 3, 2
  
     # Initialize dictionary with 
     # default value as false.
visited = defaultdict(lambda: False)
  
     # Recursive function which prints the 
     # intermediate steps to reach the final 
     # solution and return boolean value 
     # (True if solution is possible, otherwise False).
     # amt1 and amt2 are the amount of water present 
     # in both jugs at a certain point of time.
def waterJugSolver(amt1, amt2): 
  
    # Checks for our goal and 
    # returns true if achieved.
    if (amt1 == aim and amt2 == 0) or (amt2 == aim and amt1 == 0):
        print(amt1, amt2)
        return True
      
    # Checks if we have already visited the
    # combination or not. If not, then it proceeds further.
    if visited[(amt1, amt2)] == False:
        print(amt1, amt2)
      
        # Changes the boolean value of
        # the combination as it is visited. 
        visited[(amt1, amt2)] = True
      
        # Check for all the 6 possibilities and 
        # see if a solution is found in any one of them.
        return (waterJugSolver(0, amt2) or
                waterJugSolver(amt1, 0) or
                waterJugSolver(jug1, amt2) or
                waterJugSolver(amt1, jug2) or
                waterJugSolver(amt1 + min(amt2, (jug1-amt1)),
                amt2 - min(amt2, (jug1-amt1))) or
                waterJugSolver(amt1 - min(amt1, (jug2-amt2)),
                amt2 + min(amt1, (jug2-amt2))))
      
    # Return False if the combination is 
    # already visited to avoid repetition otherwise
    # recursion will enter an infinite loop.
    else:
        return False
  
print("Steps: ")
  
     # Call the function and pass the
     # initial amount of water present in both jugs.
     waterJugSolver(0, 0)
     output:
     Steps: 
     0 0
     4 0
     4 3
     0 3
     3 0
     3 3
     4 2
     0 2
     True
     #travellingSalesmanProblem
     from sys import maxsize
     from itertools import permutations
     V = 4
     def travellingSalesmanProblem(graph, s):
    vertex = []
    for i in range(V):
        if i != s:
            vertex.append(i)
    min_path = maxsize
    next_permutation=permutations(vertex)
    for i in next_permutation:
        current_pathweight = 0
        k = s
        for j in i:
            current_pathweight += graph[k][j]
            k = j
        current_pathweight += graph[k][s]
        min_path = min(min_path, current_pathweight)
    return min_path
     if __name__ == "__main__":
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
            [15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
    output
    80
          import csv
hypo=['%','%','%','%','%','%']
with open('Training_examples.csv') as csv_file:
    readcsv = csv.reader(csv_file, delimiter=',')
    data=[]
    print("\nThe given training examples are:")
    for row in readcsv:
        print(row)
        if row[len(row)-1] =='Yes':
                  data.append(row)
print("\nThe positive examples are:")
for x in data:
    print(x)
    TotalExamples=len(data)
    i=0
    j=0
    k=0
print("\nThe steps of the Find-s algorithm are\n",hypo)
list =[]
p=0
d=len(data[p])-1
for j in range(d):
    list.append(data[i][j])
    hypo=list
    for i in range(1,TotalExamples):
         for k in range(d):
            if hypo[k]!=data[i][k]:
                hypo[k]='?'
            else:
                hypo[k]
print(hypo)
print("\nThe maximally specific Find-s hypothesis for the given training examples is");
list=[]
for i in range(d):
    list.append(hypo[i])
print(list)



