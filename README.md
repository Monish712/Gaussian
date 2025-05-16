# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the numpy module and sys module to use the built-in functions for calculation
2. Get the size of the matrix from user and create empty matrix and vector
3. using for loop get elements for matrix and vector
4. Using another for loop to take each element in the matrix
5. solve row echelon form
6. perform back substitution
7. print the value in two decimal points
8. End the program
## Program:
```
'''
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: PAKANATI MONISH
RegisterNumber: 212224240109
'''
import numpy as np
import sys
n = int(input())

#Making numpy array of n x n+1 size and intializing
#to zero for storing augumented matrix
a = np.zeros((n,n+1))
x = np.zeros(n)

#reading augumented matrix coefficient
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

#applying Gauss elimination 
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('divide by zero dected!')
        
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio * a[i][k]
            
#back substitution
x[n-1] = a[n-1][n]/a[n-1][n-1]


for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j] * x[j]
        
    x[i] = x[i]/a[i][i]
    
#display solution
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')

```
## Output:
![image](https://github.com/user-attachments/assets/623c921b-0e95-4dfc-83f6-3feeeaa0acbd)
![image](https://github.com/user-attachments/assets/baaf2858-e606-4ada-a239-5246a9c409e9)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

