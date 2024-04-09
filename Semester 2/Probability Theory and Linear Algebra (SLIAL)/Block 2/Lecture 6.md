Date: 05/03/2023
Literature: Chapter 11
___
# Matrix inverses
## 11.1 Left and right inverses
Recall for a number a, its (multiplicative) inverse is the number $x$ for which $xa = 1$, which we usually denote as $x = 1 / a$ or (less frequently) $x=a^{-1}$. The inverse x exists provided $a$ is **nonzero**.

for matrix it is more complicated and one need to distinguish between left and right inverse. 

### **Left inverse.** 
A matrix $X$ that satisfyes
$$
X\;A=I
$$
is called a left inverse of A. The matrix $A$ is said to be left-invertible if a left inverse exists. Note that if $A$ has size $m*n$, a left inverse $X$ will have size $n*m$, the same dimensions as $A^T$ .

left inverse does not have to exist, and it does not have to be unique 

Examples:
* Any nonzero n-vector a, considered as an $n⨉1$ matrix, is left-invertible. For any index i with $a_i ≠ 0$, the row n-vector $x = (1/a^i)e^T_i$ satisfies $xa = 1$.

* If a matrix has more than one left inverse then it has infinitely many 
* A matrix $A$ with orthonormal columns satisfies $A^TA = I$, so it is left invertible; its transpose $A^T$ is a left inverse.

#### Left-invertibility and column independence.
if matrix $A$ has a left inverse $C$ then the columns of $A$ are linearly independent.  Suppose $Ax=0$ 
$$
0=C(Ax)=(CA)x=Ix=x
$$
the converse is also true; a matrix has a left inverse if and only if its columns are linearly independent

> [!NOTE] Generalization
> So the generalization of 'a number has an inverse if and only if it is nonzero' is 'a matrix has a left inverse if and only if its columns are linearly independent'.


#### Dimensions of left inverses.
Suppose the $m⨉n$ matrix $A$ is wide meaning $m<n$ (m is rows and n is columns). By the independence-dimension inequality, its  columns are linearly dependent, and therefore it is not left-invertible. **Only square or tall matrices can be left-invertible**.


#### Solving linear equations with a left inverse.
Suppose(meaning we suppose that the system is solvable otherwise there might be a solution. If even if a matrix is left invertible, it does not give the right to do the equation below if it is not solvable) that $Ax = b$, where $A$ is an $m * n$ matrix and $x$ is an n-vector. If $C$ is a left inverse of $A$, we have
$$
Cb=C(Ax)=(CA)x=Ix=x
$$
meaning that $x=Cb$ is a solution of the set of linear equations. 

in summary we can only use this trick if the system is solvable, otherwise one might get a result from $Cb$ that is not a solution.

In summary, a left inverse can be used to determine whether or not a solution of an over-determined set of linear equations exists, and when it does, find the unique solution.


### Right inverse
A matrix $X$ that satisfies 
$$
A\;X =I
$$
is called *right inverse* of $A$. The matrix $A$ is *right-invertible* if a right inverse exist. Any right inverse has the same dimensions as $A^T$.


#### Left and right inverse of matrix transpose.
if $A$ has a right inverse $B$, then $B^T$ is a left inverse of $A^T$, since $B^TA^T=(BA)^T=I$. 

if $A$ has a left  inverse $C$, then $C^T$ is a right inverse of $A^T$, since $C^TA^T=(CA)^T=I$. 

examples 
* A matrix is right-invertible if and only if its rows are linearly independent 
* A tall matrix cannot have a right inverse. only wide and quare matrices can be right inverted. 

#### Solving linear equations with a right inverse.
Consider the set of m linear equations in n variables $Ax = b$. Suppose $A$ is right-invertible, with right inverse $B$. This implies that $A$ is square or wide, so the linear equations $Ax = b$ are square or under-determined.

Then for any m-vector b, the n-vector $x = Bb$ satisfyes the equation $Ax = b$. To see this, we note that
$$
Ax=A(Bb)=(AB)b=Ib=b
$$
We can conclude that if A is right-invertible, then the linear equations $Ax = b$ can be solved for any vector $b$. Indeed, $x = Bb$ is a solution(there could be other solutions).

### Left and right inverse of matrix product.
Suppose $A$ and $D$ are compatible for the matrix product $AD$ (i.e., the number of columns in $A$ is equal to the number of rows in $D$.) If $A$ has a right inverse $B$ and $D$ has a right inverse $E$, then $EB$ is
a right inverse of $AD$. This follows from
$$
(AD)(EB)=A(DE)B=A(IB)=AB=I
$$
If $A$ has a left inverse $C$ and $D$ has a left inverse $F$, then $FC$ is a left inverse of $AD$. This follows from
$$
(FC)(AD)=F(CA)D=FD=I
$$
## 11.2 Inverse
If a matrix is left- and right-invertible, then the left and right inverses are unique and equal. To see this, suppose that$ AX = I$ and $Y A = I$ $X$ is any right inverse and $Y$ is any left inverse of $A$. Then we have
$$
X=(YA)X=Y(AX)=Y
$$
When a matrix $A$ has both a left inverse $Y$ and a right inverse $X$, we call the matrix $X = Y$ simply the *inverse* of $A$, and denote it as $A^{-1}$. 

We say that $A$ is invertible or non-singular. A square matrix that is not invertible is called *singular*.

### Dimensions of invertible matrices.
Invertible matrices must be square
tall matrices are not right-invertible 
wide matrices are not left invertible

A matrix $A$ and its invers (if it exists) satisfy
$$
AA^{-1}=A^{-1}A=I
$$

Inverse of inverse 
$$
(A^{-1})^{-1}=A
$$

### Invertible matrices must be square
Consider the square system of n linear equations with n variables, $Ax = b.$ If $A$ is invertible, then for any n-vector b,
Equation 11.1
$$
x=A^{-1}b
$$
is a solution of the equation

We summarize this very important result as

> [!NOTE] Important
> The square system of linear equations $Ax=b$, with $A$ invertible has the unique solution $x=A^{-1}b$ for any n-vector b.
### Invertibility conditions. (interesting read again)
For square matrices, left-invertibility, right-invertibility, and invertibility are equivalent: If a matrix is square and left-invertible, then it is also right-invertible (and therefore invertible) and vice-versa.

In summary, for a square matrix A, the following are equivalent.
* $A$ is invertible 
* The columns if $A$ ae linearly independent 
* The rows of $A$ are linearly independent 
* $A$ has a left inverse
* $A$ has a right inverse
So all six of these conditions are equivalent; if any one of them holds, so do the other five.


if a matrix si invertible 
then for any b,  $Ax=b$  has the unique solution
$$
x=A^{-1}b
$$
for matrices larger than fx 4x4 this is bad to use as it is very costly and there are more effecting ways to find the solution. However it is good that one is aware of this formula. 

### Inverse of matrix transpose.
A is invertible, its transpose $A^T$ is also invertible and its inverse is $(A^{-1})^T$ :
$$
(A^T)^{-1}=(A^{-1})^T
$$
Since the order of the transpose and inverse operations does not matter, this matrix is sometimes written as $A^{-T}$ .

### Inverse of matrix product.
If $A$ and $B$ are invertible (hence, square) and of the
same size, then$ AB$ is invertible, and
Equation 11.2
$$
(AB)^{-1}=B^{-1}A^{-1}
$$
The inverse of a product is the product of the inverses, in reverse order.

### Dual basis.
interesting


### Negative matrix powers.
Suppose $A$ is a square invertible matrix and k is a positive integer. Then by repeatedly applying property (11.2), we get
$$
(A^k)^{-1}=(A^{-1})^k
$$
We denote this matrix as $A^{k}$. For example, if $A$ is square and invertible, then $A^{-2} = A^{-1}A^{-1} = (AA)^{-1}$.

$A^0$ is defined as $A^0=I$ 

#### Inverse via QR factorization.
equation 11.3
## 11.3 Solving linear equations




