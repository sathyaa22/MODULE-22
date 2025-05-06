# EX 4B DYNAMIC PROGRAMMING – 2
## DATE: 29.04.2025
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..


## Algorithm

1. Start the program.
2. Read the input strings X and Y.
3. Let m = len(X) and n = len(Y).
4. Initialize a 2D matrix lookup of size (m+1) x (n+1) with all values set to 0.
5. Initialize two variables: maxLength = 0 and endingIndex = m.
6. Loop through the matrix from i = 1 to m and j = 1 to n:
   If X[i-1] == Y[j-1], set lookup[i][j] = lookup[i-1][j-1] + 1
   If lookup[i][j] > maxLength, update maxLength and set endingIndex = i
7. Extract the substring from X[endingIndex - maxLength : endingIndex] and return it.
8. End the program.   

## Program:
```
Program to implement the longest common substring problem
Developed by: SATHYAA R
Register Number: 212223100052
```

```
def LCS(X, Y, m, n):
    maxLength = 0
    endingIndex = m
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]

X = input()
Y = input()
m = len(X)
n = len(Y)
print('The longest common substring is', LCS(X, Y, m, n))
```


## Output:

![image](https://github.com/user-attachments/assets/513bf540-ff89-4c41-b42e-8b7c6d9a2922)


## Result:
Thus the program was executed successfully for finding the longest common substring .
