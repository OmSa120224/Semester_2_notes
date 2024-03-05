Date: 23/02/2024
Literature: Ch 10
______
# Matrix multiplication
## 10.1 Matrix-matrix multiplication
You can multiply two matrices A and B provided their dimensions are *compatible*, which means the number of columns of *A* equals the number of rows of *B*.

if A has size $m * p$ and B has size $p * n$. Then the product matrix
$C = AB$ is the $m * n$ matrix with elements
Equation
$$
C_{ij}=\sum_{k=1}^pA_{ik}B_{kj}=A_{i1}B_{1j}+...+A_{ip}B{pj},\;\;\;i=1,...,m,\;\;\;j=1,...,n
$$




### Vector outer product.
The outer product of an *m-vector* $a$ and an *n-vector* $b$ is
given by $abT$ , which is an $m * n$ matrix
![[Vector outer product.png]]
$ab^T ≠ba^T$ outer product is not symmetric

### Properties of matrix multiplication.
* *Associativity*: $(AB)C = A(BC)$. Therefore we can write the product simply as $ABC$
* *Associativity with scalar multiplication*: $\gamma(AB) = (\gamma A)B,$ where and A and B are matrices (that can be multiplied). This is also equal to $A(\gamma B)$. (Note that the products A and  B are defined as scalar-matrix products, but in general, unless A and B have one row, not as matrix-matrix products.)
* *Distributivity with addition*. Matrix multiplication distributes across matrix addition: $A(B+C) = AB+AC$ and $(A+B)C = AC+BC$. On the right-hand sides of these equations we use the higher precedence of matrix multiplication over addition, so, for example, AC + BC is interpreted as (AC) + (BC).
* *Transpose of product*. The transpose of a product is the product of the transposes, but in the opposite order: $(AB)^T = B^TA^T$ .