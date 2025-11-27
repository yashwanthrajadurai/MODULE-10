## Ex.No:2

## Ex.Name: Write A CPP Program to implement BFS using vectors and queue (use float data)

## Aim:
To write A CPP Program to implement BFS using vectors and queue (use float data)

## Algorithm:
1. Create an adjacency list using vectors to represent the graph.
2. Initialize a visited array to mark visited nodes.
3. Create a queue to process nodes level by level.
4. Start BFS from a given source vertex and mark it visited.
5. Dequeue a vertex, print it, and enqueue all its unvisited adjacent vertices.
6. Repeat until the queue becomes empty.

## Program:
```
#include <bits/stdc++.h>
#define pb push_back

using namespace std;

vector<bool> v;
vector<vector<int> > g;

void edge(int a, int b)
{
    g[a].pb(b);
    g[b].pb(a);
}

void bfs(int u)
{
	queue<int> q;
	q.push(u);
	v[u]=true;
	
	while(!q.empty())
	{
	    int n = q.front();
	    q.pop();
	    cout<<n<<" ";
	    
	    for(auto i=g[n].begin();i!=g[n].end();i++)
	    {
	        if(!v[*i])
	        {
	            q.push(*i);
	            v[*i] = true;
	        }
	    }
	}
}

int main()
{
	int n,a;
    cin>>n>>a;
    
    v.assign(n,false);
    g.assign(n, vector<int> ());
    int x,y;
    for(int i=0;i<a;i++)
    {
        cin>>x>>y;
        edge(x,y);
    }
    for(int i=0;i<n;i++)
    {
        if(!v[i])
            bfs(i);
        
    }
	return 0;
}
```


## Output:
<img width="585" height="606" alt="Screenshot 2025-11-04 175503" src="https://github.com/user-attachments/assets/3eb2b532-b213-4556-9024-c295d27503ca" />

## Result:
Thus the program created successfully to implement BFS using vectors and queue.

