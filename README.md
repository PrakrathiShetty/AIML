# AIML<br><br>
<b>1.BREADTH FIRST SEARCH</b><br>
graph={<br>
    '1':['2','10'],<br>
    '2':['3','8'],<br>
    '3':['4'],<br>
    '4':['5','6','7'],<br>
    '5':[],<br>
    '6':[],<br>
    '7':[],<br>
    '8':['9'],<br>
    '9':[],<br>
    '10':[]<br>
}<br>
visited=[]<br>
queue=[]<br>
def bfs(visited,graph,node):<br>
    visited.append(node)<br>
    queue.append(node)<br>
    while queue:<br>
        m=queue.pop(0)<br>
        print(m,end=" ")<br>
        for neighbour in graph[m]:<br>
            if neighbour not in visited:<br>
                visited.append(neighbour)<br>
                queue.append(neighbour)<br>
print("Following the BFS")<br>
bfs(visited,graph,'1')<br>

<b>2.DEPTH FIRST SEARCH</b><br> Using a Python dictionary to act as an adjacency list<br>
graph = {<br>
    '5' : ['3','7'],<br>
    '3' : ['2', '4'],<br>
    '7' : ['6'],<br>
    '6': [],<br>
    '2' : ['1'],<br>
    '1':[],<br>
    '4' : ['8'],<br>
    '8' : []<br>
}<br>
visited = set() # Set to keep track of visited nodes of graph.<br>
def dfs(visited, graph, node): #function for dfs<br>
    if node not in visited:<br>
        print (node)<br>
        visited.add(node)<br>
        for neighbour in graph[node]:<br>
            dfs(visited, graph, neighbour)<br>

Driver Code<br>
print("Following is the Depth-First Search")<br>
dfs(visited, graph, '5')<br>

<b>3.BINARY SEARCH</b><br>
Iterative Binary Search Function method Python Implementation <br>
It returns index of n in given list1 if present, <br>  
else returns -1   <br>
def binary_search(list1, n):  <br>
    low = 0  <br>
    high = len(list1) - 1  <br>
    mid = 0  <br>
  
    while low <= high:  <br>
         for get integer result   <br>
        mid = (high + low) // 2  <br>
  
        Check if n is present at mid   <br>
        if list1[mid] < n:  <br>
            low = mid + 1  <br>
  
         If n is greater, compare to the right of mid   <br>
        elif list1[mid] > n:  <br>
            high = mid - 1  <br>
  
         If n is smaller, compared to the left of mid  <br>
        else:  <br>
            return mid  <br>
  
            element was not present in the list, return -1  <br>
    return -1  <br>
  
  
Initial list1  <br>
list1 = [12, 24, 32, 39, 45, 50, 54]  <br>
n = 50<br>
  
Function call   <br>
result = binary_search(list1, n)  <br>
  
if result != -1: <br> 
    print("Element is present at index", str(result))  <br>
else:  <br>
    print("Element is not present in list1") <br> 


<b>4.BEST FIRST SEARCH</b><br> 
from queue import PriorityQueue<br> 
import matplotlib.pyplot as plt<br> 
import networkx as nx<br> 
def best_first_search(source,target,n):<br> 
    visited=[0]*n<br> 
    visited[source]=True<br> 
    pq=PriorityQueue()<br> 
    pq.put((0,source))<br> 
    while pq.empty()==False:<br> 
        u=pq.get()[1]<br> 
        print(u,end="")<br> 
        if u==target:<br> 
            break<br> 
        for v,c in graph[u]:<br> 
            if visited[v]==False:<br> 
                visited[v]=True<br> 
                pq.put((c,v))<br> 
    print()<br> 
def addedge(x,y,cost):<br> 
    graph[x].append((y,cost))<br> 
    graph[y].append((x,cost))<br> 
    
v=int(input("enter the number of nodes:"))<br> 
graph=[[] for i in range(v)]<br> 
e=int(input("Enter the number of edges:"))<br> 
print("Enter the edges along with their weights")<br> 
for i in range(e):<br> 
    x,y,z=list(map(int,input().split()))<br> 
    addedge(x,y,z)<br> 
source=int(input("Enter the source node:"))<br> 
target=int(input("enter the target/destination node:"))<br> 
print("\nPath:",end="")<br> 
best_first_search(source,target,v)<br> 


<b>5.WATERJUG PROBLEM</b><br> 
from collections import defaultdict<br> 
jug1,jug2,aim=4,3,2<br> 
visited=defaultdict(lambda:False)<br> 
def waterJugSolver(amt1,amt2):<br> 
    if(amt1==aim and amt2==0)or(amt2==aim and amt1==0):<br> 
        print(amt1,amt2)<br> 
        return True<br> 
    if visited[(amt1,amt2)]==False:<br> 
        print(amt1,amt2)<br> 
        visited[(amt1,amt2)]=True<br> 
        return(waterJugSolver(0,amt2)or<br> 
            waterJugSolver(amt1,0)or<br> 
            waterJugSolver(jug1,amt2)or<br> 
            waterJugSolver(amt1,jug2)or<br> 
            waterJugSolver(amt1+min(amt2,(jug1-amt1)),<br> 
            amt2-min(amt2,(jug1-amt1))) or<br> 
            waterJugSolver(amt1-min(amt1,(jug2-amt2)),<br> 
            amt2+min(amt1,(jug2-amt2))))<br> 
    else:<br> 
        return False<br> 
print("steps:")<br> 
waterJugSolver(0,0)<br> 

<b>6.TOWEROGHANOI</b><br> 
def TowerOfHanoi(n,source,destination,auxiliary):<br> 
    if n==1:<br> 
        print("Move desk 1 from source",source,"to destination",destination)<br> 
        return<br> 
    TowerOfHanoi(n-1,source,auxiliary,destination)<br> 
    print("Move disk",n,"form source",source,"to destination",destination)<br> 
    TowerOfHanoi(n-1,auxiliary,destination,source)<br> 
n=3<br> 
TowerOfHanoi(n,'A','B','C')<br> 


#AO* algorithem

