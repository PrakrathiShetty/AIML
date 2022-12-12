# AIML<br><br>
<b>BREADTH FIRST SEARCH</b><br>
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

<b>DEPTH FIRST SEARCH</b><br> Using a Python dictionary to act as an adjacency list<br>
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
  
        #Check if n is present at mid   <br>
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
