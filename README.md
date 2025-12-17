# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1.Input matrix dimensions and initialize augmented matrix and solution vector.

2.Populate the augmented matrix with user inputs.

3.Perform Gaussian elimination to reduce the matrix to upper triangular form, ensuring no division by zero.

4.Back substitute to compute solution values for the variables.

5.Print the solution vector formatted to two decimal places.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: ishwar
RegisterNumber: 25017577
*/
```
```
import numpy as np
def solve(data):
    n=int(data[0])
    A=np.array(data[1:],dtype=float).reshape(n,n+1)
    
    for i in range(n):
        for j in range(i+1,n):
            factor=A[j,i]/A[i,i]
            A[j]-=factor*A[i]
    
    x=np.zeros(n)
    for i in range(n-1,-1,-1):
        x[i]=(A[i,-1]-np.dot(A[i,i+1:n],x[i+1:n]))/A[i,i]
    
    return x

data=[]
for i in range(13):
    data.append(input())
    
result=solve(data)
print("".join([f"X{i} = {val:.2f} " for i,val in enumerate(result)]))
```

## Output:

<img width="951" height="878" alt="Screenshot 2025-12-17 105920" src="https://github.com/user-attachments/assets/880f5c75-2abb-48d9-b6fe-fca2794cf3e6" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

