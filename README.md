# LU Decomposition 

## AIM:
To write a program to find the LU Decomposition of a matrix.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. 
2. 
3. 
4. 

## Program:
(i) To find the L and U matrix
```
/*
Program to find the L and U matrix.
Developed by: 
RegisterNumber: 
*/
```
(ii) To find the LU Decomposition of a matrix
```
/*
'''Program to find L and U matrix using LU decomposition.
Developed by: Hemavarathan S
RegisterNumber: 25005365
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"

import numpy as np
A=np.array(eval(input()),dtype=float)
n=len(A)
U=A.copy()
L=np.eye(n)
for K in range(n-1):
    #Partial pivoting
    p=np.argmax(np.abs(U[K:,K]))+K
    if p!=K:
        U[[K,p]]=U[[p,K]]
    if K>0:
        L[[K,p],:K]=L[[p,K],:K]
    for i in range(K+1,n):
        L[i,K]=U[i,K]/U[K,K]
        U[i]=U[i]-L[i,K]*U[K]
print(L)
print(U): 
*/
```

## Output:
<img width="1167" height="434" alt="image" src="https://github.com/user-attachments/assets/e19f987e-c317-4510-9bd5-731858233349" />


## Result:
Thus the program to find the LU Decomposition of a matrix is written and verified using python programming.

