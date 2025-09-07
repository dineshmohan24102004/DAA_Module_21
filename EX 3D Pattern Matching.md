# EX 3D Pattern Matching
## DATE:
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
Start the program.

Read two strings:

s1 → the text string.

s2 → the pattern string.

Define the function BF(s1, s2) that:

Initialize two indices i = 0 (text) and j = 0 (pattern).

While i < len(s1) and j < len(s2):

If s1[i] == s2[j], increment both i and j.

Else, shift the text pointer by one (i = i - j + 1) and reset j = 0.

After the loop:

If j >= len(s2), return the starting index of the match → i - len(s2).

Otherwise, return 0 (pattern not found).

In the main program:

Take user input for a1 (text) and a2 (pattern).

Call BF(a1, a2) and store the result in b.

Print the result.

Stop the program.   

## Program:
```
/*
Program to implement the Pattern Matching.
Developed by: Dinesh M
Register Number: 212222040039

def BF(s1,s2):
##############  Add your code here #############
    #Start here
    i = 0
    j = 0
    while(i < len(s1) and j < len(s2)):
        if(s1[i] ==  s2[j]):
            i += 1
            j += 1
        else:
            i = i - j + 1
            j = 0
    if(j >= len(s2)):
        return i - len(s2)
    else:
        return 0
    #End here
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)

*/
```

## Output:

<img width="1187" height="327" alt="Screenshot 2025-09-07 180239" src="https://github.com/user-attachments/assets/6216d048-db9c-4a98-bc1f-a7aa542447a7" />


## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
