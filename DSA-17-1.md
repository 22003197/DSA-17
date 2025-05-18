# Data-Structures-using-Python-17-1

## AIM :

To write a Python program to perform Depth First Search (DFS) traversal from a given source vertex using a helper function DFSUtil.

## ALGORITHM:

Step 1 : Define a graph using an adjacency list (dictionary format).

Step 2 : Create a helper function DFSUtil(v, visited, graph):

a) Mark the current node as visited.

b) Print the current node.

c) Recursively call DFSUtil for all adjacent nodes that are not yet visited.

Step 3: In the main function:

a) Initialize a visited list to keep track of visited vertices.

b) Get the starting vertex as input from the user.

c) Call DFSUtil with the source vertex and graph.

Step 4 : Display the order of visited vertices during the DFS traversal.

## PROGRAM:

```
from collections import defaultdict



class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self, u, v):
		self.graph[u].append(v)

	# A function used by DFS
	def DFSUtil(self, v, visited):

		# Mark the current node as visited
		# and print it
		visited.add(v)
		print(v,end=' ')
		for neighbour in self.graph[v]:
		    if neighbour not in visited:
		        self.DFSUtil(neighbour, visited)
		
		
	# The function to do DFS traversal. It uses
	# recursive DFSUtil()
	def DFS(self, v):

		# Create a set to store visited vertices
		visited = set()

		# Call the recursive helper function
		# to print DFS traversal
		self.DFSUtil(v, visited)


n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print("Following is DFS from (starting from vertex {})".format(n))
g.DFS(n)
```

## OUTPUT:

![image](https://github.com/user-attachments/assets/38d24331-54f9-4ba6-a746-c70eb3eaa6d3)

## RESULT :

Thus the program to perform Depth First Search (DFS) traversal from a given source vertex using a helper function DFSUtil was successfully verified.
