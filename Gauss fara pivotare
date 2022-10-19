#SubDesc
import numpy as np
def verif_cond_inf_triung(L,b):
    if np.shape(L)[0]!=np.shape(L)[1]:
        print('Mat sist nu e patratica')
        return
    
    if np.shape(L)[0]!=np.shape(b)[0]:
        print('Mat sist nu e compatibil cu vect dpdv al dim')
        return
    
    for i in range(0,np.shape(L)[0]):
        if L[i,i]==0:
            print('Mat sist nu e inv')
            return
        for j in range(i+1,np.shape(L)[1]):
            if L[i,j]!=0:
                print('Mat sist nu e inf triung')
                return
    print('Se poate aplica met subst asc')

def SubsAsc(L,b):
    n=np.shape(L)[1]
    # n=len(b)
    x=np.zeros((n,1))
    x[0]=b[0]/L[0,0]
    for k in range(1,n):
        x[k]=(b[k]-L[k,0:k]@x[0:k])/L[k,k]
    
    return x

L=np.array([[2.0,1,0],
            [-1,4,0],
            [-2,4,1]
           ])
b=np.array([[2.],
            [3],
            [3]])
x=SubsAsc(L,b)
print(x)
def CondSubDesc(U,b):
    if np.shape(U)[0]!=np.shape(U)[1]:
        print("Matricea sistemului nu este patratica")
        return False
    if np.shape(U)[0]!=np.shape(b)[0]:
        print("Matricea si vectorul nu sunt compatibili")
        return False
    for i in range(0,np.shape(U)[0]):
        if U[i,i]==0:
            print("Matricea sist nu este inv")
            return False
        for j in range(i):
            if U[i,j]!=0:
                print("Matricea nu este sup tr")
                return False
    return True
def SubDesc(U,b):
   if CondSubDesc(U,b)==0:   
     return False
   else:
       n=np.shape(U)[0]
       x=np.zeros((n,1))
       x[n-1]=b[n-1]/U[n-1,n-1]
       for i in range(n-2,-1,-1):
           x[i]=(b[i]-U[i,i+1:n]@x[i+1:n])/U[i,i]
   return x
U=np.array([[2.0,1,1],
            [-1,4,1],
            [-2,4,1]
           ])
b=np.array([[2.],
            [3],
            [3]])
x=SubDesc(U,b)
print(x)    
def GaussFP(A,b):
    if CondSubDesc(A,b)==0:
        return False
    else:
        Aext=np.hstack((A,b))
        n=np.shape(A)[0]
        for k in range(n-1):
            if A[k,k]==0:
                return False
            for i in range(k+1,n):
                
