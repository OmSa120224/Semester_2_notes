**Scheduled**: 2024/02/16
**Latest Revision**: 2024/05/09
**Literature**: Introduction to Applied Linear Algebra: Vectors, Matrices, and Least Squares by S. Boyd and L. Vandenberghe.  **Chapter 6 & 7**.
___
# Chapter 6 Matrices

## 6.1 Matrices
A matrix is a rectangular array of numbers written between rectangular brackets.

$$
\begin{bmatrix}0\ \;\; 1\ -2.3\ \;\;\; 0.1\\ 1.3\ \;\; 4\ -0.1\ \;\; 0\\ 4.1\ -1\ \;\;\; 0\ \;\;1.7 \end{bmatrix}
$$

An important attribute of a matrix is its *size* or *dimensions*, i.e., the numbers of *rows* and *columns*. The matrix above has 3 rows and 4 columns, so its size is $3⨉4$. A matrix of size $m ⨉ n$ is called an $m ⨉ n$ matrix.

The *elements* (or *entries* or *coefficients*) of a matrix are the values in the array. The $i, j$ element is the value in the $i_{th}$ row and $j_{th}$ column.

Two matrices are equal if they have the same size, and the corresponding entries are all equal.

### Square, tall, and wide matrices.
A square matrix has an equal number of rows and columns. A square matrix of size $n⨉n$ is said to be of order $n$. 
A tall matrix has more rows than columns (size $m⨉n$ with $m > n$). 
A wide matrix has more columns than rows (size $m⨉n$ with $n > m$).


### Column and row vectors.
We do not distinguish between vectors and matrices with one column. In other words, an $n-$vector is just an $n⨉1$ matrix.


### Columns and rows of a matrix.
An $m⨉n$ matrix $A$ has $n$ columns, given by
$$
a_j=\begin{bmatrix}A_{1j}\\ \vdots \\ A_{mj}\end{bmatrix}
$$
for $j = 1,...,n$. The same matrix has $m$ rows, given by the ($n-row-vectors$) 
$$
b_i=\begin{bmatrix}A_{i1}\ \dots \ A_{in}\end{bmatrix}
$$
for $i = 1, ..., m$.

### Block matrices and submatrices.
It is useful to consider matrices whose entries are themselves matrices, as in
$$
A=\begin{bmatrix}B\ \;\;\;C \\ D \;\;\; E \end{bmatrix}
$$
$B$, $C$, $D$ and $E$ are  called *submatrices*.

Block matrices must have the right dimensions to fit together.
 - Matrices in the same (block) row must have the same number of rows
- Matrices in the same (block) column must have the same number of columns

### Column and row representation of a matrix.
Using block matrix notation we can write an $m ⨉ n$ matrix $A$ as a block matrix with one block row and $n$ block columns.
$$
A= \begin{bmatrix}a_1\ \; a_2\ \; \dots\ \; a_n \end{bmatrix}
$$
Similarly, an $m ⨉ n$ matrix A can be written as a block matrix with one block
column and m block rows:
$$
A=\begin{bmatrix}b_1\\b_2\\ \vdots \\ b_m \end{bmatrix}
$$

### The slicing notation for matrices.
let $A$ be a $3⨉4$ matrix.
$$
A= \begin{bmatrix}0\ \; 2\ \; 3 \ \; -1\\     2\ \; \; 2\ \; 1\ \; \; 4 \\ 1\ \;\; 3\ \; 5\ \;\;4 \end{bmatrix}
$$
Then the submatrix $A_{2:3,3:4}$ is obtained by extracting the elements from the rows 2 through 3 and the columns 3 through 4.  
$$
A_{2:3,3:4}= \begin{bmatrix}1\ \; \; 4\\  5\ \;\; 4 \end{bmatrix}
$$

### Matrix representation of a relation or graph.
A relation can  be viewed as a directed graph, with nodes (or vertices) labelled $1,..., n$, and a directed edge from $j$ to $i$ for each $(i,j) \in R$.  meaning the pair $(1,3)$ is the vertex from 3 to 1. 

The relation $R=\{(1,2), (1,3), (2,1), (2,4), (3,4), (4,1) \}$ is represented as a directed graph below.
![[SLIAL lecture 3 relation graph 6.1.png]]
This matrix is called the *adjacency matrix* and is associated with the graph 6.1. 
$$
A= \begin{bmatrix}0\ \ \ 1\ \ \ 1\ \ \ 0\\  1\ \ \ 0\ \ \ 0\ \ \ 1\\ 0\ \ \ 0\ \ \ 0\ \ \ 1\\ 1\ \ \ 0\ \ \ 0\ \ \ 0 \end{bmatrix}
$$
(Some authors define the *adjacency matrix* in the reverse sense, with $A_{ij} = 1$ meaning there is an edge from $i$ to $j$.)
___ 
## 6.2 Zero and identity matrices

### Identity matrix. 
 An identity matrix is always square and Its diagonal elements, i.e., those with equal row and column indices, are all equal to one, and its off-diagonal elements (those with unequal row and column
indices) are zero. Identity matrices are denoted by the letter $I$. 

Formally, the identity matrix of size $n$ is dened by
$$
I_{ij}=\begin{cases}1\ \ \ i=j \\ 0\ \ \ i \neq j, \end{cases}
$$
for $i,j=1,...,n$. For example 
$$
\begin{bmatrix}1\ \ \ 0\ \ \ 0\ \ \ 0\\ 0\ \ \ 1\ \ \ 0\ \ \ 0\\ 0\ \ \ 0 \ \ \ 1\ \ \ 0\\ 0\ \ \ 0\ \ \ 0\ \ \ 1 \end{bmatrix}
$$
The column vectors of the $n ⨉ n$ identity matrix are the unit vectors of size n. Using block matrix notation, we can write
$$
I=[e_1\ \ \ e_2\ \ \ \dots \ \ \ e_n]
$$
where  $e_k$ is the $k_{th}$ unit vector of size $n$.

### Sparse matrices.
A matrix $A$ is said to be *sparse* if many of its entries are zero, or (put another way) just a few of its entries are nonzero.

The number of nonzero entries of a sparse matrix $A$ is the number of entries in its sparsity pattern, and denoted $nnz(A)$. 

The *density* denotes as $nnz(A)/(mn)$ which is no more than one.

Note: There is no precise definition of how small the density must be for a matrix to qualify as sparse.

The identity matrix is a sparse matrix, has $n$ nonzero entries and its density is $n/n^2$ or $1/n$.

### Diagonal matrices.
A square $n ⨉ n$ matrix $A$ is diagonal if $A_{ij} = 0$ for $i \neq j$. 

The entries of a matrix with $i = j$ are called the *diagonal entries*; those with $i \neq j$ are its *off-diagonal* entries.

Examples: Square zero matrices and identity matrices. Another example 
$$
\begin{bmatrix}0.2\ \ \ 0\ \ \ 0\ \ \ 0\\ 0\ \ \ 1\ \ \ 0\ \ \ 0\\ 0\ \ \ 0 \ \ \ 4\ \ \ 0\\ 0\ \ \ 0\ \ \ 0\ \ \ 6 \end{bmatrix}
$$
### Triangular matrices.
square $n ⨉ n$ matrix $A$ is upper triangular if $A_{ij} = 0$ for
$i > j$, and it is lower triangular if $A_{ij} = 0$ for $i < j$. 

 A diagonal matrix is one that is both lower and upper triangular
 If a matrix is either lower or upper triangular, it is called *triangular*.
$$
 A=\begin{bmatrix}2\ \ \ \ 1\ \ \ -5\\ 0\ \ \ \ 1\ \ \ -8\\ 0\ \ \  \  0 \ \ \ \ \ 4 \end{bmatrix}, \;\;\;\;\; B= \begin{bmatrix}2\ \ \ \ 0\\ 5\ \ \ \ 1 \end{bmatrix}
$$
The matrix $A$ is a lower triangular and the matrix $B$ is upper triangular. 
____
## 6.3 Transpose, addition, and norm

### Matrix transpose
If A is an $m⨉n$ matrix, its transpose, denoted $A^T$, is the $n ⨉ m$ matrix given by $(A^T )_{ij} = A_{ji}$. In other words, the rows and columns of $A$ are transposed in $A_T$ . For example
$$
\begin{bmatrix}0\ \ 4\\ 7 \ \ 0\\ 3\ \ 1 \end{bmatrix}^T=\begin{bmatrix} 0\ \ 7\ \ 3 \\ 4\ \ 0\ \ 1 \end{bmatrix}
$$
If we transpose a matrix twice, we get back the original matrix: $(A^T )^T = A$.

### Row and column vectors.
Transposition converts row vectors into column vectors and vice versa. It is common to extend concepts from (column) vectors to row vectors, by applying the concept to the transposed row vectors. We say that a collection of row vectors is linearly dependent (or independent) if their transposes (which are column vectors) are linearly dependent (or independent). For example, the rows
of a matrix $A$ are linearly independent means that the columns of $A^T$ are linearly independent.

### Transpose of block matrix.
The transpose of a block matrix has the simple form
$$
\begin{bmatrix}A\ \;\;\;B \\ C \;\;\; D \end{bmatrix}^T = \begin{bmatrix}A^T\ \;\;\;B^T \\ C^T \;\;\; D^T \end{bmatrix}
$$
where $A$, $B$, $C$, and $D$ are matrices with compatible sizes.

### Symmetric matrix.
A square matrix $A$ is *symmetric* if $A = A^T$ , i.e., $A_{ij} = A_{ji}$
for all $i, j$.  

For example, suppose that $A$ is the adjacency matrix of a graph or relation. The matrix $A$ is symmetric when the relation is symmetric, i.e., whenever $(i, j) \in R$, we also have $(j, i) \in R$. 

This is the same thing as in set theory and relations
___
### 6.3.2 Matrix addition
Two matrices of the same size can be added together. The result is another matrix of the same size, obtained by adding the corresponding elements of the two matrices. For example,
$$
\begin{bmatrix}0\ \ 4\\ 7 \ \ 0\\ 3\ \ 1 \end{bmatrix}+\begin{bmatrix}1\ \ 2\\ 2 \ \ 3\\ 0\ \ 4 \end{bmatrix} = \begin{bmatrix}1\ \ 6\\ 9 \ \ 3\\ 3\ \ 5 \end{bmatrix}
$$
Matrix subtraction is similar 
$$
\begin{bmatrix}1\ \ 6\\ 9 \ \ 3\end{bmatrix}-I=\begin{bmatrix}0\ \ 6\\ 9\ \ 2 \end{bmatrix}
$$
#### Properties of matrix addition.
- *Commutativity*. $A + B = B + A$.
- *Associativity*. $(A + B) + C = A + (B + C)$. We therefore write both as $A + B + C$.
- Addition with zero matrix. $A + 0 = 0 + A = A$. Adding the zero matrix to a matrix has no effect.
- Transpose of sum. $(A + B)^T = A^T + B^T$ . The transpose of a sum of two matrices is the sum of their transposes.
___
### 6.3.3 Scalar-matrix multiplication
Scalar multiplication of matrices is dened in a similar way as for vectors, and is done by multiplying every element of the matrix by the scalar. For example
$$
(-2)\begin{bmatrix}0\ \ 4\\ 7 \ \ 0\\ 3\ \ 1 \end{bmatrix}=\begin{bmatrix}0\ \ \  -8\\ -14 \ \ \ \ 0\\ -6\ \ -2 \end{bmatrix}
$$
Properties of scalar multiplication follow directly from the definition.
For example , $( \beta A)^T = \beta (A^T)$ for a scalar $\beta$ and a matrix $A$. If $A$ is a matrix and $\beta$,  $\theta$  are scalars, then
$$
(\beta + \theta)A=\beta A + \theta A, \;\;\;\;\;\;\; (\beta \theta)A=\beta (\theta A)
$$
___
### 6.3.4 Matrix norm
The norm of an $m⨉n$ matrix $A$, denoted $||A||$, is the squareroot of the sum of the squares of its entries,
$$
||A|| = \sqrt{\Sigma_{i=1}^m \Sigma_{j=1}^n\;\;A^2_ij}
$$

#### Properties of norm
The properties of matrix norm is the same as the properties of the vector norm.
* $Nonnegative\; homogeneity$. $$|| \beta A|| = | \beta |\: || A ||$$Multiplying a matrix  by a scalar multiplies the norm by the absolute value of the scalar.
* $Triangle\; Inequality$. $$|| A + B|| ≤ ||A||+||B||$$ The norm of a sum of two matrices is no more than the sum of theirs norms. Also called *subadditivity*.
* $Nonnegativity$. $$||A||≥0 $$
* $Definiteness$. $||A|| = 0$ only if $A =0$

Additional properties 
- The norm of a matrix is equal to the norm of its transpose
$$
||A|| = ||A^T||
$$
- The squared norm of a matrix is the sum of the squared norms of its columns.  $$||A||^2= ||a_1||^2+...+||a_n||^2 $$
_____
## 6.4 Matrix-vector multiplication
If A is an $m⨉n$ matrix and $x$ is an $n-$vector, then the matrix-vector product $y = Ax$ is the $m-$vector $y$ with elements 
$$
y_i=\Sigma_{k=1}^n\;\; A_{ik}x_k=A_{i1}x_1+...+A_{in}x_n,\;\;\;\;\;\;i=1,...,m\;\;\;\;\;\;\;(6.4)
$$
For example 
$$
\begin{bmatrix}0\ \ \ 2\ \ \ -1\\ -2\ \ \ 1\ \ \ 1 \end{bmatrix} \begin{bmatrix}2\\ 1\\ -1 \end{bmatrix}=\begin{bmatrix}(0)(2)+(2)(1)+(-1)(-1) \\ (-2)(2)+ (1)(1) +(1)(-1)\end{bmatrix}= \begin{bmatrix} 3\\ -4\end{bmatrix}
$$
#### Row and column interpretations.
We can express the matrix-vector product in terms of the rows or columns of the matrix. From (6.4) we see that $y_i$ is the inner product between the vector $x$ and the $i_{th}$ row of $A$.
$$
y_i=b_i^Tx,\;\;\;\;i=1,...,m
$$
where $b_i^T$ is the row $i$ of $A$.  Here $y_i$ is the $i_{th}$ elements of the resulting vector. 


The matrix-vector product can also be interpreted in terms of the columns of $A$. if $a_k$ is the $k_{th}$ column of $A$, then $y = Ax$ can be
written
$$
y=x_1a_1+x_2a_2+...+x_na_n
$$

Note in the above we are multiplying a single element if vector $x$ with a whole column of matrix $A$, which gives us the result of $Ax$. 



_____
#### Linear dependence of columns. 
We can express the concepts of linear dependence and independence in a compact form using matrix-vector multiplication.

The columns of a matrix $A$ are linearly dependent if $Ax = 0$ for some $x \neq 0$. 
The columns of a matrix $A$ are linearly independent if $Ax = 0$ implies $x = 0$.
___
#### Expansion in a basis. 
If the columns of $A$ are a basis, which means $A$ is square with linearly independent columns $a_1,...,a_n$, then for any $n-$vector $b$ there is a unique $n-$vector $x$ that satisfies $Ax = b$. In this case the vector $x$ gives the coefficients in the expansion of $b$ in the basis $a_1,...,a_n$.
______
#### Properties of matrix-vector multiplication.
Pay attention to the overloading of signs.
First, it distributes across the vector argument: For any $m ⨉ n$ matrix $A$ and any $n-$vectors $u$ and $v$, we have
$$
A(v+u)=Av+Au
$$
Matrix-vector multiplication also distributes across the matrix argument: For any $m ⨉ n$ matrices $A$ and $B$, and any $n-$vector $u$, we have
$$
(A+B)u=Au+Bu
$$
Another basic property is, for any $m ⨉ n$ matrix A, any $n-$vector $u$, and any scalar $\alpha$, we have
$$
(\alpha A)u=\alpha (Au)
$$
which is the same as $\alpha A u$
________
# Chapter 7 Matrix examples
This chapter describes some special matrices that occur often in applications.
## 7.1 Geometric transformations

## 7.2 Selectors

## 7.3 Incidence matrix
## 7.4 Convolution
