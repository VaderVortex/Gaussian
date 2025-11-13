# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. **Take the inputs**  
   - Read how many equations there are.  
   - Read all the numbers of the augmented matrix.

2. **Check for impossible division**  
   - For every step, make sure the number you’re about to divide by is not zero.

3. **Clear the values below each pivot**  
   - For each row, remove the numbers under the current leading value by subtracting a suitable multiple of the pivot row.

4. **Start solving from the bottom**  
   - Calculate the last variable first using the last row.

5. **Solve the rest of the variables upward**  
   - For each row above, subtract the already-found values and then divide to get the new variable.

6. **Print the final answers**  
   - Display each variable rounded to two decimal places.

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

