# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
3.	Obtain the Q matrix   
4.	Construct the upper triangular matrix R
5. finally print the Q and R matrix
6. end the program


## Program:
### Gram-Schmidt Method
``` 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Panduru somu
RegisterNumber: 212223240111

import numpy as np
def QR_Decomposition(A):
    n,m = A.shape
    
    q = np.empty((n,n))
    u = np.empty((n,n))
    u[:,0]=A[:,0]
    q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    
    for i in range(1,n):
        
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i] -=(A[:,i] @ q[:,j]) * q[:,j]
            
        q[:,i] = u[:,i] /np.linalg.norm(u[:,i])
    R= np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j] = A[:,j] @ q[:,i]
            
    print(q)
    print(R)
    
    
a = np.array(eval(input()))
QR_Decomposition(a)








```

## Output
![Screenshot 2023-12-30 172834](https://github.com/Pandurusomu/QRdecomposition/assets/148988619/86219ffb-40c2-4ced-8e6d-ca045ae29571)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
