# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
## Step 1:
Import the numpy module to use the built-in functions for calculation.
## Step 2:
Import the sys module to use the builit-in funtions.
## Step 3:
Get input from the user for number of rows and add it by 1 for number of columns.
## Step 4:
using np.zeroz() set the matrix as null matrix 
## step 5:
using nested for loop get input from the matrix
## Step 6:
using nested for loop find the ratio and perform the final matrix.
## Step 7:
Use back substitution mathod to find the value of the variables and print it.
## Step 8:
End the program

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: DURGA V
RegisterNumber:23013532 
*/
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][j] == 0.0:
        sys.exit('Divide by zero detected!')
    
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
        
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')
```

## Output:
![Alt text](<Screenshot 2023-12-30 174557.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

