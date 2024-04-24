# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by:Mohanram Gunasekar
RegisterNumber: 212223240095
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,m))
    R=np.zeros((n,m))
    u=np.empty((n,m))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(n):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    for i in range(n):
        for j in range(i,n):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
    
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output
```
![Screenshot 2024-04-24 075814](https://github.com/MohanramGunasekar/QRdecomposition/assets/139841812/c4b10369-944c-4d82-8c2d-499d6da16463)

![Screenshot 2024-04-24 075833](https://github.com/MohanramGunasekar/QRdecomposition/assets/139841812/d70f5d67-88a9-45cd-9d82-63800c6c0309)

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
