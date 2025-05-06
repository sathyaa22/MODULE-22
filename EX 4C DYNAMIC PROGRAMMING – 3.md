# EX 4C DYNAMIC PROGRAMMING – 3
## DATE: 02.05.2025
## AIM:
To find the length of the longest palindromic subsequence in it.


## Algorithm

1. Start the program.
2. Read the input string X and determine its length n.
3. Create a 2D array dp of size n x n and initialize all values to 0.
4. Set all diagonal elements dp[i][i] = 1, since a single character is a palindrome of length 1.
5. For each substring length l from 2 to n:
   For each starting index i, compute the ending index j = i + l - 1
   If X[i] == X[j], set dp[i][j] = dp[i+1][j-1] + 2
   Else, set dp[i][j] = max(dp[i+1][j], dp[i][j-1])
6. After filling the table, dp[0][n-1] contains the length of the longest palindromic subsequence.
7. Return dp[0][n-1] as the result.
8. End the program.


## Program:
```
Program to implement to find the length of the longest palindromic subsequence in it
Developed by: SATHYAA R
Register Number: 212223100052
```

```
def Lps(X):
    n=len(X)
    dp=[[0 for _ in range(n)] for _ in range(n)]
    for x in range(n):
        dp[x][x]=1
    for l in range(2,n+1):
        for i in range(n-l+1):
            j=i+l-1
            if X[i]==X[j]:
                dp[i][j]=dp[i+1][j-1]+2
            else:
                dp[i][j]=max(dp[i+1][j],dp[i][j-1])
    return dp[0][n-1]
X=input()
print("The length of the LPS is",Lps(X))
```


## Output:

![image](https://github.com/user-attachments/assets/00956b83-7411-4428-9ff4-b531ae908efd)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
