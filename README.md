# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
    ![ex4](https://github.com/ARCHANAT1305/QRdecomposition/assets/145975189/485593ea-3e53-4387-8ee2-8ecf30a68679)
    ![ex6](https://github.com/ARCHANAT1305/QRdecomposition/assets/145975189/e302001a-444a-4a28-ae56-8e721064f238)
    ![ex3](https://github.com/ARCHANAT1305/QRdecomposition/assets/145975189/1db1a188-cc11-47ff-ab60-ab897fe58b12)

  

3.	Obtain the Q matrix   
   ![ex1](https://github.com/ARCHANAT1305/QRdecomposition/assets/145975189/336eea46-b088-4f9b-a1c0-702d42ceabf1)

4.	Construct the upper triangular matrix R
   ![ex2](https://github.com/ARCHANAT1305/QRdecomposition/assets/145975189/d4ba372f-58eb-4bae-ae6d-d0eea0561568)

## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: ARCHANA.T
RegisterNumber: 212223240013
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=A[:,0] /np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i] -= (A[:,i] @ Q[:,j]) * Q[:, j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i]) 
    R =np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
    
a = np.array(eval(input()))
QR_Decomposition(a)
```

## Output
![QR decompposition](https://github.com/ARCHANAT1305/QRdecomposition/assets/145975189/5fc8b42a-4a86-4a01-a8e5-b4291dfd6970)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.



