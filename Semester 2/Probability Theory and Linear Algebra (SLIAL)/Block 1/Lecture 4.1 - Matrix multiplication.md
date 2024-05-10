Self Study (w/o help)
**Scheduled**: 2024/02/23
**Latest Revision**: 2024/05/09
**Literature**: Introduction to Applied Linear Algebra: Vectors, Matrices, and Least Squares by S. Boyd and L. Vandenberghe.  **Chapter 10**.
______
# Matrix multiplication
In this chapter we introduce matrix multiplication, a generalization of matrix-vector multiplication, and describe several interpretations and applications.

## 10.1 Matrix-matrix multiplication
You can multiply two matrices $A$ and $B$ provided their dimensions are *compatible*, which means the number of columns of $A$ equals the number of rows of $B$.

if $A$ has size $m ⨉ p$ and $B$ has size $p ⨉ n$. Then the product matrix
$C = AB$ is the $m ⨉ n$ matrix with elements
Equation 10.1
$$
C_{ij}=\sum_{k=1}^pA_{ik}B_{kj}=A_{i1}B_{1j}+...+A_{ip}B{pj},\;\;\;i=1,...,m,\;\;\;j=1,...,n
$$
To find the $i, j$ element of the product $C = AB$, you need to know the $i_{th}$ row of $A$ and the $j_{th}$ column of $B$. The summation above can be interpreted as moving left to right along the $i_{th}$ row of $A$ while moving top to bottom down the $j_{th}$ column of $B$. As you go, you
keep a running sum of the product of elements, one from $A$ and one from $B$.
![[SLIAL Lecture 4.1 matrix matrix multiplication example.png]]
____
### Inner product.
An important special case of matrix-matrix multiplication is the
multiplication of a row vector with a column vector. If $a$ and $b$ are $n-$vectors, then the inner product
$$
a^Tb=a_1b_1+a_2b_2+...+a_nb_n
$$
can be interpreted as the matrix-matrix product of the $1 ⨉ n$ matrix $a^T$ and the $n⨉1$ matrix $b$. The result is a $1⨉1$ matrix, which we consider to be a scalar. (This explains the notation $a^T b$ for the inner product of vectors $a$ and $b$ , defined in [[Lecture 1 - Introduction, Vectors and Linearity]] 
_____
### Vector outer product.
The outer product of an $m-$vector $a$ and an $n-$vector $b$ is given by $ab^T$ , which is an $m ⨉ n$ matrix 
![[Vector outer product.png]]
$ab^T ≠ba^T$ outer product is not symmetric
_____
### Properties of matrix multiplication.
* *Associativity*: $(AB)C = A(BC)$. Therefore we can write the product simply as $ABC$
* *Associativity with scalar multiplication*: $\gamma(AB) = (\gamma A)B,$ where and $A$ and $B$ are matrices (that can be multiplied). This is also equal to $A(\gamma B)$. (Note that the products $A$ and  $B$ are defined as scalar-matrix products, but in general, unless $A$ and $B$ have one row, not as matrix-matrix products.)
* *Distributivity with addition*. Matrix multiplication distributes across matrix addition: $A(B+C) = AB+AC$ and $(A+B)C = AC+BC$. On the right-hand sides of these equations we use the higher precedence of matrix multiplication over addition, so, for example, $AC + BC$ is interpreted as $(AC) + (BC)$.
* *Transpose of product*. The transpose of a product is the product of the transposes, but in the *opposite* order: $(AB)^T = B^TA^T$ .
_____
### Products of block matrices.
![[SLIAL Lecture 4.1 products of block matricies.png]]
This is the same as the formula for multiplying two $2⨉2$ matrices (with scalars entries).  
_____
### Column interpretation of matrix-matrix product.
We can derive some additional insight into matrix multiplication by interpreting the operation in terms of the columns of the second matrix. Consider the matrix product of an $m ⨉ p$ matrix $A$ and a $p ⨉ n$ matrix $B$, and denote the columns of $B$ by $b_k$. Using block-matrix notation, we can write the product $AB$ as
$$
AB=A[b_1\ \ b_2 \ \ \dots \ \ b_n]=[Ab_1\ \ Ab_2 \ \ \dots \ \ Ab_n]
$$
Thus, the columns of $AB$ are the matrix-vector products of $A$ and the columns of $B$. The product $AB$ can be interpreted as the matrix obtained by "applying" $A$ to each of the columns of $B$.
____
### Row interpretation of matrix-matrix product.
nice know, but unimportant for now

____
### Inner product representation
From the definition of the $i, j$ element of $AB$ , we also see that the elements of $AB$ are the inner products of the rows of $A$ with the columns of $B$:
$$
AB=\begin{bmatrix} a^T_1b_1\ \ a^T_1b_2\ \ \dots \ \  a^T_1b_n\\ 
a^T_2b_1\ \ a^T_2b_2 \ \ \dots \ \ a^T_2b_n \\
\vdots \ \ \ \ \ \  \ \ \vdots \ \ \ \ \ \ \ \ddots \ \ \ \ \ \ \ \vdots \\
a^T_mb_1\ \ a^T_mb_2 \ \ \dots \ \ a^T_mb_n
\end{bmatrix}
$$
where $a^T_i$ are the rows of $A$ and $b_j$ are the columns of $B$. Thus we can interpret the matrix-matrix product as the $mn$ inner products $a^T_i bj$ arranged in an $m ⨉ n$ matrix.
___
### Gram matrix.
$$
G = A^TA
$$
____
### Outer product representation.
If we express the $m ⨉ p$ matrix $A$ in terms of its columns $a_1,..., a_p$ and the $p ⨉ n$ matrix $B$ in terms of its rows $b^T_1,..., b^T_p$
$$
A=[a_1\ \ \dots \ \ a_p], \;\;\;\; B=\begin{bmatrix} b^T_1 \\ \vdots \\ b^T_p \end{bmatrix}
$$
then we can express the product matrix $AB$ as a sum of outer  products:
$$
AB=a_1b^T_1+ \dots + a_pb^T_p
$$
______
## 10.2 Composition of linear functions
### Matrix-matrix products and composition.
Suppose $A$ is an $m⨉p$ matrix and $B$ is $p ⨉ n$. We can associate with these matrices two linear functions $f : R^p \to R^m$ and $g : R^n \to R^p$, defined as $f(x) = Ax$ and $g(x) = Bx$. The composition of the
two functions is the function $h : R^n \to R^m$ with
$$
h(x)=f(g(x))=A(Bx)=(AB)x
$$

Why $AB \neq BA$
![[SLIAL Lecture 4.1 why AB ≠ BA.png]]
_____
### Second difference matrix.



____
## 10.3 Matrix power
It makes sense to multiply a square matrix $A$ by itself to form $AA$. We refer to this matrix as $A^2$ (we can only take the power of square matrices). 

Similarly, if $k$ is a positive integer, then $k$ copies of $A$ multiplied together is denoted $A^k$. If $k$ and $l$ are positive integers, and $A$ is square, then $A^kA^l = A^{k+l}$ and $(A^k)^l = A^{kl}$. 

By convention we take $A^0 = I$, which makes the formulas above hold for all nonnegative integer values of $k$ and $l$.



### Paths in a directed graph.
Suppose $A$ is the $n⨉n$ adjacency matrix of a directed graph with $n$ vertices:
$$
A=\begin{cases}1\;\;\; there\; is\; a\; edge\; from\; vertex \; j\; to \; vertex\;i \\ 0 \;\;\; othewise \end{cases}
$$
Example 
![[SLIAL Lecture 4.1 figure 10.1 directed graph example.png]]

The adjacency matrix $A$ for the graph in figure 10.1. 
![[SLIAL Lecture 4.1 matrix for directed graph figure 10.1.png]]

___
## 10.4 QR factorization
### Matrices with orthonormal columns.
As an application of Gram matrices, we can express the condition that the $n-$vectors $a_1,..., a_k$ are orthonormal in a simple way using matrix notation:
$$
A^TA=I
$$
where $A$ is the $n⨉k$ matrix with columns $a_1,...,a_k$.
There is no standard term for a matrix whose columns are orthonormal: We refer to a matrix whose columns are
orthonormal as "a matrix whose columns are orthonormal".

But a square matrix that satisfies $A^TA = I$ is called *orthogonal*; its columns are an orthonormal basis.


### Norm, inner product, and angle properties.
Suppose the columns of the $m ⨉ n$ matrix $A$ are orthonormal, and $x$ and $y$ are any $n-$vectors. We let $f : R^n \to R^m$ be the function that maps $z$ to $Az$. Then we have the following:
- $||Ax|| = ||x||$. That is $f$ is *norm preserving*  
- $(Ax)^T(Ay)=x^Ty$. $f$ preserves the inner product between vectors
- $\angle(Ax,Ay)=\angle(x,y)$. $f$ also preserves angles between vectors.
  
_____
### QR factorization.

> [!NOTE] video
> Link: https://www.youtube.com/watch?v=vDCZpK96k7k&list=PLoROMvodv4rMz-WbFQtNUsUElIh2cPmN9&index=29
> QR factorization starts at 10:43


