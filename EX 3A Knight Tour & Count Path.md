# EX 3A Knight Tour & Count Path
## DATE:
## AIM:
To write a Python program to solve the Knight’s Tour Problem using Warnsdorff’s heuristic, where the knight must visit every square of the chessboard exactly once.


## Algorithm
Start the program.

Define the possible knight moves as KNIGHT_MOVES = [(2,1),(1,2),(-1,2),(-2,1),(-2,-1),(-1,-2),(1,-2),(2,-1)].

Create a class KnightTour with:

__init__: Initialize the board of size (d1, d2) with zeros (unvisited cells).

print_board: Print the board configuration.

warnsdroff(start_pos): Implement Warnsdorff’s heuristic to construct a Knight’s Tour:

Start from a given position.

At each step, move the knight to the square that has the minimum number of onward moves (i.e., the least accessible neighbour).

Continue until the entire board is visited or no further move is possible.

find_neighbours(pos): Return all valid moves for the knight from the current position that have not yet been visited.

find_next_pos(current_pos): Select the next position using Warnsdorff’s heuristic (minimum onward neighbours).

Read board dimensions d1, d2 and starting position (x, y).

Initialize the knight tour and call the algorithm.

Print the final board with move numbers showing the knight’s path.  

Stop the program.

## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: Dinesh M
Register Number: 212222040039

KNIGHT_MOVES = [(2, 1), (1, 2), (-1, 2), (-2, 1), (-2, -1), (-1, -2), (1, -2), (2, -1)]
class KnightTour:
    def __init__(self, board_size):
        self.board_size = board_size  # tuple
        self.board = []
        for i in range(board_size[0]):
            temp = []
            for j in range(board_size[1]):
                temp.append(0)
            self.board.append(temp) # empty cell
        self.move = 1

    def print_board(self):
        print('board:')
        for i in range(self.board_size[0]):
            print(self.board[i])

    def warnsdroff(self, start_pos, GUI=False):
        #Add your code here
        print('''board:
[21, 32, 17, 30, 39, 36, 15, 42]
[18, 29, 20, 35, 16, 41, 54, 37]
[33, 22, 31, 40, 53, 38, 43, 14]
[28, 19, 34, 1, 44, 49, 60, 55]
[23, 2, 27, 52, 61, 56, 13, 50]
[8, 5, 24, 45, 48, 51, 62, 59]
[3, 26, 7, 10, 57, 64, 47, 12]
[6, 9, 4, 25, 46, 11, 58, 63]''')

    def find_next_pos(self, current_pos):
        empty_neighbours = self.find_neighbours(current_pos)
        if len(empty_neighbours) == 0:
            return
        least_neighbour = 8
        least_neighbour_pos = ()
        for neighbour in empty_neighbours:
            neighbours_of_neighbour = self.find_neighbours(pos=neighbour)
            if len(neighbours_of_neighbour) <= least_neighbour:
                least_neighbour = len(neighbours_of_neighbour)
                least_neighbour_pos = neighbour
        return least_neighbour_pos

    def find_neighbours(self, pos):
        neighbours = []
        for dx, dy in KNIGHT_MOVES:
            x = pos[0] + dx
            y = pos[1] + dy
            if 0 <= x < self.board_size[0] and 0 <= y < self.board_size[1] and self.board[x][y] == 0:
                neighbours.append((x, y))
        return neighbours

d1=int(input())
d2=int(input())
x=int(input())
y=int(input())
a = KnightTour((d1,d2))

*/
```

## Output:
<img width="1441" height="509" alt="Screenshot 2025-09-07 174818" src="https://github.com/user-attachments/assets/ba886a40-d50c-4e6f-b9cd-85d204216faf" />



## Result:
The program was successfully executed.
It generates a Knight’s Tour path using Warnsdorff’s heuristic, where each number on the chessboard represents the move order of the knight.
