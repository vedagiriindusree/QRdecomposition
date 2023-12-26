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
Developed by: Vedagiri Indu sree
RegisterNumber: 23004520
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=a[:,0]
    q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=a[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@q[:,j]*q[:,j])
        q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    r=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            r[i,j]=A[:,j]@q[:,i]
    print(q)
    print(r)
    
    
a = np.array(eval(input()))
QR_Decomposition(a)

## Output
![image](https://github.com/vedagiriindusree/QRdecomposition/assets/149366776/930c503e-9fa4-4182-8d6a-752f0528ac34)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
