# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Enter the number of equations and read the augmented matrix (coefficients + constants).
2. Apply row operations to make all elements below the main diagonal equal to zero.
(Use operations like R₂ → R₂ − kR₁, etc.)
3. Start from the last equation and substitute values upward to find all unknowns.
4. Print the values of the variables (solution of the system).

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: kamali v
RegisterNumber: 212225240066
*/
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1),dtype=float)
for i in range (n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range (n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range (n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x=np.zeros(n)
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range (n-2,-1,-1):
    x[i]=a[i][n]
    for j in range (i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    if i==0:
        print("X%d = %.2f" %(i,x[i]),end=" ")
    else:
        print("X%d = %.2f" %(i,x[i]),end=" ")
```

## Output:
![alt text](<Screenshot 2026-03-26 090511.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

