## Ex.No:4

## Ex.Name: Write A C++ Graph implementation using STL for competitive programming | (DFS of Unweighted and Undirected)

## Aim:
To write A C++ Graph implementation using STL for competitive programming.

## Algorithm:
1. Start the program.
2. Read number of vertices and edges.
3. Create an adjacency list using vector of vectors.
4. For each edge, insert both directions (u → v and v → u) since graph is undirected.
5. Initialize a visited vector to keep track of visited nodes.
6. Perform DFS from a given starting node.
7. In DFS, mark the node as visited and print it.
8. Recursively visit all unvisited adjacent vertices.
9. Stop the program

## Program:
```
#include <bits/stdc++.h>
using namespace std;
void addEdge(vector<int> adj[], int u, int v)
{
    adj[u].push_back(v);
}

void DFS(vector<int> adj[], int v, vector<bool> &vis)
{
    vis[v] = true;
    cout<<v<<" ";
    for(auto i :adj[v])
    {
        if(vis[i] == false)
        {
            DFS(adj, i , vis);
        }
    }
}

int main()
{ 
    int n ,a,b;
    cin>>n;
    vector<int>adj[n];
    vector<bool>visited(n,false);
    for(int i = 0 ;i < n ;i++)
    {
        cin>>a>>b;
        addEdge(adj,a,b);
    }
    DFS(adj, 1, visited);
}
```


## Output:
<img width="574" height="831" alt="Screenshot 2025-11-04 180358" src="https://github.com/user-attachments/assets/58e57c87-8ea4-4c23-ad4f-0d297d73a1bf" />



## Result:
Thus the program created successfully for Graph implementation using STL for competitive programming .

