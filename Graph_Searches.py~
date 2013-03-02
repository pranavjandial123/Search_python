'''by Soumyadeep ghosh'''

'''SEARCH ALGORITHMS IMPLEMENTED BY AAYUSH KOTHARI. Feel free to use the code for reference as long as my signature is retained.'''
'''Map used in this graph can be found at : http://centurion2.com/AIHomework/Searching/RomaniaMap.JPG'''
def dfs(graph, start,end, path=[]):
  
  q=[start]	#q is basically a stack, the data-structure most efficient for a DFS.
  while q:
	v=q.pop(0)
	if v==end:
	  break
	if not v in path:
	  path=path+[v]
	  if graph[v]==[]:
		continue
	  q=graph[v]+q #this is where this (stack) is different from the queue implemented below in bfs.
  path=path+[end]
  return path

def bfs(graph, start,end, path=[]):
  
  q=[start] #q here is a Queue, the data-structure used for performing a BFS.
  while q:
	v=q.pop(0)
	if v==end:
	  break
	if not v in path: #add unvisited nodes to the path
	  path=path+[v]
	  if graph[v]==[]: #if leaf-city, do nothing and re-iterate
		continue
	  q=q+graph[v] #add children of current node to the Queue
  path=path+[end]
  return path

def dls(graph, start,end,limit, path=[]):
  
  q=[start]
  depth=0
  
  while q:
    v=q.pop(0)
    depth=depth+1 #update the depth for each new city visited
    if v==end:
        path=path+[v]
        break
    if not v in path: #adding unvisited cities to path
	  path=path+[v]
	  if graph[v]==[]:
		continue
    if depth==limit:
        while depth!=1: #keep going back till the beginning city in order to begin visiting it's other connected cities.
            depth=depth-1
    else:
        q=graph[v]+q
	#print path
	
  #path=path+[end]
  return path 

def ids(graph,start,end):
	limit=1
	while(limit!=10): #I have hard-set the limit to 10 here. Theoritically, it is supposed to be infinity, so feel free to change it.
		path=dls(graph,start,end,limit)
		if end in path:
			print "Depth limit: "+str(limit)+"-> ",path
			break
		else:
			print "Depth limit: "+str(limit)+"-> ",path
			limit=limit+1

graph = {'O': ['Z', 'S'],
			 'Z': ['A'],
			 'A':['T','S'],        
			 'T': ['L'],
			 'L':['M'],
			 'M':['D'],
			 'D':['C'],
			 'C':['R','P'],
			 'S':['R','F'],
			 'R':['S','P'],
			 'F':['B'],
			 'P':['B'],
			 'B':['G','U'],
			 'U':['H','V'],
			 'H':['E'],
			 'V':['I'],
			 'I':['N'],
			 'G':[],
			 'E':[],
			 'N':[]
			 } 
print "\n\nLet's explore Romania!", "\n","DFS=Depth First Search, BFS=Breadth First search","\n","DLS=Depth-Limited Search and IDS=Iterative Deepening Search"
print "\n", "Cities are represented by their initial alphabet IN CAPS!","\n"
start=str(raw_input("Enter Starting Node: "))
end=str(raw_input("Enter Destination: "))
lim=int(raw_input("Enter limit (for DLS): "))
print 'DFS: ', dfs(graph, start,end)
print '\nBFS: ', bfs(graph, start,end)
route= dls(graph,start,end,lim)
print '\nDLS: '
if end not in route:
	print end+" not present within the given limit("+str(lim)+")"
print "Map explored: ",route

print "\nIDS:\n "
ids(graph,start,end)
print "\n","This also demonstrates that (usually) IDS provides us with the shortest path as it explores all possible paths at each (limited) iteration"
