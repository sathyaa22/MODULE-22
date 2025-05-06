# EX 4A DYNAMIC PROGRAMMING - 1
## DATE: 29.04.2025
## AIM:
To find longest common subsequence using Dynamic Programming.


## Algorithm

1. Start the program
2. Read input strings str1 and str2.
3. Let m = len(str1) and n = len(str2).
4. Create a 2D matrix of size (m+1) x (n+1) and initialize all elements to 0.
5. Loop through the matrix from i = 1 to m and j = 1 to n:
   If str1[i-1] == str2[j-1], set matrix[i][j] = 1 + matrix[i-1][j-1]
   Else, set matrix[i][j] = max(matrix[i-1][j], matrix[i][j-1])
6. After filling the matrix, the value at matrix[m][n] holds the length of the LCS.
7. Return matrix[m][n] as the result.
8. End the program.
  

## Program:
```
Program to implement the longest common subsequence using Dynamic Programming
Developed by: SATHYAA R
Register Number: 212223100052
```

```
def lcs(str1 , str2):
    m = len(str1)
    n = len(str2)
    matrix = [[0]*(n+1) for i in range(m+1)] 
    for i in range(m+1):
        for j in range(n+1):
            if i==0 or j==0:
                matrix[i][j] = 0
            elif str1[i-1] == str2[j-1]:
                matrix[i][j] = 1 + matrix[i-1][j-1]
            else:
                matrix[i][j] = max(matrix[i-1][j] , matrix[i][j-1])
    return matrix[-1][-1]
str1 = input()
str2 = input()
lcs_length = lcs(str1, str2)
print("Length of LCS is : {}".format(lcs_length))
```


## Output:

![image](https://github.com/user-attachments/assets/9e083110-7f56-445b-b668-4f180fdba4b9)


## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
