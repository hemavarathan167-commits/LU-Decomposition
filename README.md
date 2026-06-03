# LU Decomposition 

## AIM:
To write a program to find the LU Decomposition of a matrix.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import the required NumPy and SciPy libraries.
2.Get the matrix elements from the user and store them in a matrix form.
3.Use the scipy.linalg.lu() function to perform LU Decomposition of the given matrix.
4.Display the Lower triangular matrix (L) and Upper triangular matrix (U) as the output. 
## Program:
(i) To find the L and U matrix
```
/*
'''Program to find L and U matrix using LU decomposition.
Developed by: Hemavarathan S
RegisterNumber: 25005365

# To print X matrix (solution to the equations)
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"

import numpy as np
A=np.array(eval(input()),dtype=float)
B=np.array(eval(input()),dtype=float)
n=len(A)
L=np.eye(n)
U=A.copy()

for K in range(n-1):
    p=np.argmax(np.abs(U[K:,K]))+K
    if p!=K:
        U[[K,p]]=U[[p,K]]
        B[[K,p]]=B[[p,K]]
        
        if K>0:
            L[[K,p],:K]=L[[p,K],:K]
    for i in range(K+1,n):
        L[i,K]=U[i,K]/U[K,K]
        U[i]=U[i]-L[i,K]*U[K]

y=np.zeros(n)
for i in range(n):
    y[i]=B[i]-np.dot(L[i,:i],y[:i])
x=np.zeros(n)
for i in range(n-1,-1,-1):
    x[i]=(y[i]-np.dot(U[i,i+1:],x[i+1:]))/U[i,i]
        
        
print(x)        
        
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
<img width="1013" height="181" alt="image" src="https://github.com/user-attachments/assets/082d5893-0845-4e99-ae71-5b123699cd88" />


## Result:
Thus the program to find the LU Decomposition of a matrix is written and verified using python programming.

