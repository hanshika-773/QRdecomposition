# Date:
# Ex.No 8: Algorithm for QR Decomposition
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
import numpy as np
def QR_Decomposition(A):
   m,n=A.shape
   Q=np.zeros((m,n))
   R=np.zeros((m,n))
   for j in range(n):
       v=A[:,j]
       for i in range(j):
           R[i,j]=np.dot(Q[:,i],v)
           v= v-R[i,j]*Q[:,i]
       R[j,j]=np.linalg.norm(v)
       Q[:,j]=v/R[j,j]
   return Q, R
a = np.array(eval(input()))
Q,R=QR_Decomposition(a)
print(Q)
print(R)

```
## Output
![Screenshot 2024-10-16 150101](https://github.com/user-attachments/assets/e37de5a2-7bb1-4856-852f-b0614bec75a1)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
