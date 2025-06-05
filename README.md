# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input matrix dimensions and initialize augmented matrix and solution vector.
2. Populate the augmented matrix with the user inputs.
3. Perform Gaussian Elimination to reduce the matrix to upper triangular form, ensuring no division by zero.
4. Back Substitute to compute solution values for the variables.
5. Print the solution vector formatted to two decimal places

## Program:
```

Program to find the solution of a matrix using Gaussian Elimination.
Developed by: RAHUL S
RegisterNumber: 212224040259
```

    import numpy as np
    import sys
    n = int(input())
    a = np.zeros((n,n+1))
    x = np.zeros(n)
    for i in range(n):
        for j in range(n+1):
            a[i][j] = float(input())
    for i in range(n):
        if a[i][i] ==0.0:
            sys.exit('Divide by zero detected')
        for j in range(i+1,n):
            ratio = a[j][i]/a[i][i]
            for k in range(n+1):
                a[j][k] = a[j][k]-ratio*a[i][k]
    x[n-1] = a[n-1][n]/a[n-1][n-1]
    for i in range(n-2,-1,-1):
        x[i] = a[i][n]
        for j in range(i+1,n):
            x[i]=x[i]-a[i][j]*x[j]
        x[i] = x[i]/a[i][i]
        
    for i in range(n):
        print("X%d = %0.2f "%(i,x[i]),end='')


## Output:
![image](https://github.com/user-attachments/assets/ee257dcb-65b4-47a0-91cd-f270110f8297)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.9
