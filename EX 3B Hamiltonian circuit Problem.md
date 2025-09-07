# EX 3B Hamiltonian Circuit Problem
## DATE:
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
Start the program.

Represent the graph using an adjacency matrix adj[N][N], where adj[i][j] = 1 indicates an edge between vertex i and j.

Initialize a 2D DP table dp[N][1<<N], where dp[i][mask] = True means there exists a path that visits the set of vertices represented by mask and ends at vertex i.

Base Case: For each vertex i, set dp[i][1<<i] = True (a path starting and ending at the same vertex).

For each subset of vertices mask:

For each vertex j in mask:

For each vertex k in mask:

If adj[k][j] == 1 and dp[k][mask ^ (1<<j)] == True, then set dp[j][mask] = True.

After filling the DP table, check if there exists a vertex i such that dp[i][(1<<N) - 1] == True.

If yes, a Hamiltonian Path exists.

Otherwise, no Hamiltonian Path exists.

Print the result.

Stop the program.

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: Dinesh M
Register Number: 212222040039
def Hamiltonian_path(adj, N):
    dp = [[False for i in range(1 << N)] for j in range(N)]
    for i in range(N):
         dp[i][1 << i]=True
    for i in range(1 << N):
        for j in range(N):
            if ((i & (1 << j))!=0):
                for k in range(N):
                    if((i & (1 << k)) != 0 and
                            adj[k][j] == 1 and
                                    j != k and
                          dp[k][i ^ (1 << j)]):
                       dp[j][i]=True
                       break
    for i in range(N):
        if (dp[i][(1 << N)-1]):
            return True
    return False
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
if (Hamiltonian_path(adj,N)):
    print("YES")
else:
    print("NO")
 

*/
```

## Output:

<img width="1312" height="324" alt="Screenshot 2025-09-07 175027" src="https://github.com/user-attachments/assets/6c2392f9-782c-4afc-95bd-7723785154eb" />


## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
