# EX 3C Sudoku Solver
## DATE:
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


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
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: Dinesh M
Register Number: 212222040039

board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    for i in range(0,9):
        for j in range(0,9):
            if board[i][j] == 0:
                for val in range(1,10):
                    if isPossible(board, i, j, val):
                        board[i][j] = val
                        solve()
                        board[i][j] = 0
                        
                return 
    printBoard(board)
    
    #####################  Add your code here #########################
solve()
*/
```

## Output:
<img width="1331" height="489" alt="Screenshot 2025-09-07 175214" src="https://github.com/user-attachments/assets/21c43148-3fe8-4cd6-8471-c7134176a260" />



## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
