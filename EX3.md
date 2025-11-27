## Ex.No: 3

## Ex.Name: Write A C++ Program to represent the Adjacency Matrix

## Aim:
To write A C++ Program to represent the Adjacency Matrix

## Algorithm:
1. Start the program.
2. Read the number of vertices and edges.
3. Initialize the adjacency matrix with all zeros.
4. For each edge, read the vertices u and v.
5. Display the adjacency matrix.
6. Stop the program.

## Program:
```
#include<iostream>
using namespace std;
int vertArr[20][20]; 
int count = 0;
void displayMatrix(int v) 
{
    int i,j;
    for(i=0;i<v;i++)
    {
        for(j=0;j<v;j++)
        {
            cout<<vertArr[i][j]<<" ";
        }
        cout<<endl;
    }
}
void add_edge(int u, int v) 
{      
    vertArr[u][v] = 1;
    vertArr[v][u] = 1;
  
}
int main() 
{
    int x=6,a,b;
   for(int i=0;i<6;i++)
   {
       cin>>a>>b;
        add_edge(a,b);
   }
   displayMatrix(x);
   return 0;
   return 0;
}
```


## Output:
<img width="750" height="835" alt="Screenshot 2025-11-04 180053" src="https://github.com/user-attachments/assets/b0508ef9-3e8c-4e52-9395-8d333e3a0c04" />

## Result:
Thus the program created successfully to represent the Adjacency Matrix.

