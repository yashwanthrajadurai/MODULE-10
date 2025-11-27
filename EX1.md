## Ex.No:1

## Ex.Name:Write A C++ Program for Topological Sorting (using List and Stack)

## Aim:
To write A C++ Program for Topological Sorting (using List and Stack)


## Algorithm:
1. Start and initialize adjacency list for the graph.
2. Initialize a visited array to mark visited nodes.
3. Create an empty stack to store the topological order.
4. For each unvisited vertex, call the DFS function.
5. In DFS, mark the current node as visited.
6. Visit all unvisited adjacent vertices recursively.
7. After visiting all adjacent nodes, push the current node onto the stack.
8. After DFS for all vertices, pop elements from the stack to get the topological order.

## Program:
```
#include <iostream>
#include <list>
#include <stack>
using namespace std;

class Graph {
	int V; // No. of vertices'

	// Pointer to an array containing adjacency listsList
	list<int>* adj;

	// A function used by topologicalSort
	void topologicalSortUtil(int v, bool visited[], stack<int>& Stack);

public:
	Graph(int V); // Constructor

	// function to add an edge to graph
	void addEdge(int v, int w);

	// prints a Topological Sort of the complete graph
	void topologicalSort();
};

Graph::Graph(int V)
{
	this->V = V;
	adj = new list<int>[V];
}

void Graph::addEdge(int v, int w)
{
	adj[v].push_back(w); // Add w to v’s list.
}

// A recursive function used by topologicalSort
void Graph::topologicalSortUtil(int v, bool visited[],
								stack<int>& Stack)
{
	// Mark the current node as visited.
	visited[v] = true;

	// Recur for all the vertices adjacent to this vertex
	list<int>::iterator i;
	for (i = adj[v].begin(); i != adj[v].end(); ++i)
		if (!visited[*i])
			topologicalSortUtil(*i, visited, Stack);

	// Push current vertex to stack which stores result
	Stack.push(v);
}

// The function to do Topological Sort. It uses recursive
// topologicalSortUtil()
void Graph::topologicalSort()
{
    stack<int> Stack;
	
	bool* visited = new bool[V];
	
	for (int i = 0; i < V; i++)
		visited[i] = false;

	for (int i = 0; i < V; i++)
		if (visited[i] == false)
			topologicalSortUtil(i, visited, Stack);

	while (Stack.empty() == false)
	{
		cout << Stack.top() << " ";
		Stack.pop();
	}
	//write code
}

// Driver program to test above functions
int main()
{
     int a,b,n;
	cin>>n;
	Graph g(n);
	for(int i=0;i<6;i++)
	{
	 cin>>a>>b;
	 g.addEdge(a, b);
	}
	 cout << "Topological Sort of the given graph n"<<endl;
	 g.topologicalSort();
	return 0;
}
```


## Output:
<img width="1016" height="681" alt="Screenshot 2025-11-04 175033" src="https://github.com/user-attachments/assets/e23a530e-da77-46cd-9a1a-cc4aaa190393" />

## Result:
Thus the program created successfully for Topological Sorting.


