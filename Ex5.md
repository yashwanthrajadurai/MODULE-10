## Ex.No:5

## Ex.Name: Write A C++ Program to implementation DFS using Vector STL 

## Aim:
To write A C++ Program to implementation DFS using Vector STL 

## Algorithm:
1. Start the program.
2. Read number of vertices and edges.
3. Create an adjacency list using a vector of vectors.
4. For each edge, insert both directions (u → v and v → u) for undirected graph.
5. Initialize a visited vector to track visited vertices.
6. Define a DFS function to visit nodes recursively.
7. In DFS, mark current node as visited and print it.
8. Visit all unvisited adjacent nodes recursively.
9. Call DFS from the starting vertex.
10. Stop the program

## Program:
```
#include<bits/stdc++.h>
#define pb push_back
using namespace std;
vector<bool>v;
vector<vector<int>>g;
void edge(int a,int b)
{
    g[a].pb(b);
}
void bfs(int u)
{
    queue<int>q;
    q.push(u);
    v[u]=true;
    while(!q.empty())
    {
        int f=q.front();
        q.pop();
        cout<<f<<" ";
        for(auto i=g[f].begin();i!=g[f].end();i++)
        {
            if(!v[*i])
            {
                q.push(*i);
                v[*i]=true;
            }
        }
    }
}
int main()
{
    int n,e;
    cin>>n>>e;
    v.assign(n,false);
    g.assign(n,vector<int>());
    int a,b;
    for(int i=0;i<n;i++)
    {
        cin>>a>>b;
        edge(a,b);
    }
    for(int i=0;i<n;i++)
    {
        if(!v[i])
        {
            bfs(i);
        }
    }
    return 0;
}
```


## Output:
<img width="688" height="775" alt="Screenshot 2025-11-04 180741" src="https://github.com/user-attachments/assets/56b145fc-8738-44cc-be8d-07a357f81cd9" />



## Result:
Thus the porgram created successfully to implementation DFS using Vector STL 


