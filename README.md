# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

### **Step 1: Read all the inputs**
- First, take the number of equations.
- Then read all the values of the augmented matrix (the left side + the constants).

### **Step 2: Make sure the math won’t break**
- Before doing any division, check that the pivot number isn’t zero.
- If it *is* zero, the process can’t continue.

### **Step 3: Clear the numbers below each pivot**
- For each row, remove the values under the current leading number.
- You do this by subtracting a scaled version of the pivot row from the rows below it.

### **Step 4: Begin solving from the bottom row**
- Start with the last equation.
- Solve for the last variable directly since the row now has only one unknown.

### **Step 5: Work your way upward**
- For each row above, subtract the contributions of the variables you’ve already solved.
- Then divide by the pivot to get the next variable.

### **Step 6: Print the results**
- Finally, display each variable, nicely rounded to two decimal places.


## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by : SANJEEV KUMAR S
RegisterNumber: 212224040290
'''
import numpy as np
import sys

n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
        
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!');
        
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio*a[i][k]
    
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    
    x[i] = x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %.2f' %(i,x[i]), end = ' ')
```

## Output:
<img width="623" height="833" alt="image" src="https://github.com/user-attachments/assets/a0841fdc-8282-4f47-b9ed-880b23bca285" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

