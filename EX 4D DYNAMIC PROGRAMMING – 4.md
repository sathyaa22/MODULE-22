# EX 4D DYNAMIC PROGRAMMING – 4
## DATE: 02.05.2025
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.


## Algorithm
1. Start the program.
2. Read input strings x and y.
3. Let m = len(x) and n = len(y).
4. If m == 0, return n (all insertions needed). If n == 0, return m (all deletions needed).
5. If x[m-1] == y[n-1], recursively compute edit distance for x[0..m-2] and y[0..n-2].
6. If characters differ, consider the minimum of the three recursive operations:
   Replace (ed(x, y, m-1, n-1))

   Insert (ed(x, y, m, n-1))

   Delete (ed(x, y, m-1, n))
7. Return the minimum value.
8. End the program.

   
## Program:

```
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method
Developed by: SATHYAA R
Register Number: 212223100052
```

```
def ed(x,y,m,n):
    if m==0:
        return n
    if n==0:
        return m
    if x[m-1]==y[n-1]:
        return ed(x,y,m-1,n-1)
    return 1+min(ed(x,y,m-1,n-1),ed(x,y,m,n-1),ed(x,y,m-1,n))
x=input()
y=input()
print("Edit Distance",ed(x,y,len(x),len(y)))
```


## Output:

![image](https://github.com/user-attachments/assets/74fa04a4-b4b8-4e9a-b7da-ffdd70bc3459)


## Result:
Thus the program was executed successfully for finding edit distance between two strings.
