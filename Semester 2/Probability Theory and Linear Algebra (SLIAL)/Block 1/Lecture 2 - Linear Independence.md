Self-Study with Help
**Scheduled**: 2024/02/13
**Latest Revision**: 2024/05/02
**Literature**: Introduction to Applied Linear Algebra: Vectors, Matrices, and Least Squares by S. Boyd and L. Vandenberghe.  **Chapter 5**.
_____
# Chapter 5: Linear independence
## 5.1 Linear dependence

A collection or list of $n-$vectors $\vec a_1,...,\vec a_k$ (with k>1) is called *linearly dependent* if 
$$\beta_1 \vec a_1+...+ \beta_k \vec a_k=\vec0 $$
hold for some $\beta_1,...,\beta_k$ ==that are NOT all zero==. In other words, we can form the zero vector as a linear combination of the vectors, with coefficients that are not all zero. Linear dependence of a list of vectors does not depend on the ordering of the vectors in the list.

The linear dependence can also be defined in the following way. If a collection of $n$-vectors $a_1,...,a_k$ is linearly depended, then at least one of the vectors can be expressed as a linear combination of the other vectors. 
$$
\vec a_i={\beta_1 \over -\beta_i}\vec a_1+...+{\beta_{i-1} \over -\beta_i}\vec a_{i-1}+{\beta_{i+1} \over -\beta_i}\vec a_{i+1}+...+{\beta_k \over -\beta_i}\vec a_k
$$
#### Examples
* A list consisting of a single vector is linearly dependent only if the vector is zero, which also means that the scalar $\beta$ ==is cannot be zero(remember the definition)==
* A list of two $n$-vectors $a_1$ and $a_2$ is linearly dependent only if one $a_i$ is a multiple of the other (they are on the same line). For example  $$a_2=\alpha_1 a_1$$
### Linearly independent vectors.
Collection of $n$-vectors $\vec a_1,..., \vec a_k$ (with $k ≥ 1$) is called linearly independent if it is not linearly dependent, which means that
Equation 5.1
$$\beta_1 \vec a_1+...+ \beta_k \vec a_k=\vec 0 $$
only hold for $\beta_1=...=\beta_k=0$. In other words, the only linear combination of the vectors that equals the zero vector is the linear combination with all coefficients zero.

An equivalent definition is, for $n$-vectors  $a_1,..., a_k$, no $a_i$ can be expressed as a linear combination of the other vectors.

> [!NOTE]
> It must be remembered that linear dependence/independence is an attribute of a collection of vectors, and not individual vectors.

#### Example
* The standard unit $n-vectors\; e_1,...,e_n$ are linearly independent. To see this, suppose that (5.1) holds. We have $$0= \beta_1e_1+,..,+\beta_ne_n= \left[\;\; \begin{matrix} \beta_1 \\.\\.\\.\\ \beta_n \end{matrix} \;\;\right] $$
* So we conclude that $\beta_1 =...=\beta_n=0$ 

### Linear combinations of linearly independent vectors
Suppose a vector $x$ is a linear combination of linearly independent vectors $a_1,...,a_k$
$$
x=\beta_1a_1+...+\beta_ka_k
$$
When the vectors $a_1,...,a_k$ are *Linearly independent*, the coefficients that form $x$ are *unique*. If we also have
$$
x=\theta_1a_1+...+\theta_ka_k
$$
Then $\beta_i = \theta_i$ for $i=1,...,k$. This tells us that, in principle at least, we can find the coefficients that from a vector $x$ as a linear combination of linearly independent vectors.

To see this, we subtract the two equation above to get 
$$ 
x-x=(\beta_1-\theta_1)a_1+...+(\beta_k-\theta_k)a_k=0
$$
Since  $a_1,...,a_k$ are linearly independent, we conclude that $\beta_i -\theta_i$ are all zero.

* A list of vectors is linearly independent if and only if for any linear combination of them, we can infer or deduce the associated coefficients.
* If we can form a  vector $x$ of linearly independent vectors, there is only one way of doing that. Meaning the weights/coefficients are determined uniquely.

### Supersets and subsets.
- If a collection of vectors is linearly dependent, then any superset of it is linearly dependent. In other words: If we add vectors to a linearly dependent collection of vectors, the new collection is also linearly dependent. 
- Any nonempty subset of a linearly independent collection of vectors is linearly independent. In other words: Removing vectors from a collection of vectors preserves linear independence.

___
## 5.2 Basis
### Independence-dimension inequality
if the $n$-vectors $a_1,...,a_k$ are linearly independent then $k≤n$. 
* In other words a *linearly independent collection* of $n-$vectors can have at most $n$ elements.
Put another way 
* Any *collection* of $n + 1$ or more $n-$vectors is *linearly dependent*.
Example:
![[Figure 5.1 independence-dimension.png]]

### Basis
A collection of $n$ linearly independent $n$-vectors (a collection of linearly independent vectors of the maximum size) is called *basis*. 

If the $n$-vectors $a_1,...,a_n$ are a basis, then any $n$-vector $b$ can be written as a linear combination of them. 

> [!NOTE]
> Any $n$-vector $b$ can be written in a unique way as a linear combination of a *basis* $a_1,..., a_n$.

(own words might be wrong)
In a space of $n$ dimensions there can only be at most $n$ vectors that are independent. if we add another vectors $b$ to the space, then the collection of vectors is not independent anymore, and is dependent instead. When a collection of vectors is dependent at least on of the vectors in the collection can be written as a combination of the other vectors.

### Expansion in a basis.
When we express an $n-$vector b as a linear combination of
a basis  $a_1, a_2, ..., a_n$, we refer to
$$b=\alpha_1 a_1+...+\alpha_n a_n$$
as the *expansion* of $b$ in the $a_1, a_2, ..., a_n$ basis. The numbers $\alpha_1,...,\alpha_n$ are called the coefficients of the expansion of $b$ in the basis $a_1, a_2, ..., a_n$.

Example if basis:
The unit vectors 


### Proof of independence-dimension inequality
page 104
____
## 5.3 Orthonormal vectors
A collection of vectors $a_1,...,a_k$ is *orthogonal* or mutually orthogonal if $a_i \perp a_j$ for any $i,j$ with $i≠j,\;i,j=1,...,k$.

A collection of vectors $a_1,...,a_k$ is *orthonormal* if it is 
1. orthogonal and 
2. $||a_i||=1$ for $i=1,...,k$. 

A vector of norm one is called *normalized*; dividing a vector by its norm is called *normalizing* it. Thus, each vector in an orthonormal collection of vectors is normalized, and two different vectors from the collection are orthogonal.

These two conditions can be combined into one statement about the inner products of pairs of vectors in the collection: $a_1,...,a_k$ is orthonormal means that
$$
a_i^Ta_j=  \{\begin{matrix}1\;\;\; i=j\\ 0\;\;\; i≠j \end{matrix}
$$

> [!NOTE] Orthonormality
> Orthonormality, like linear dependence and independence, is an attribute of a collection of vectors, and not an attribute of vectors individually.

### Linear independence of orthonormal vectors.
Orthonormal vectors are linearly independent. Proof page 105.

(own words might be wrong)
Orthonormal vectors are linearly independent, because each vector is in its own dimension. Think of two vectors in 2D space that are perpendicular to each other, on u want to add another vector that is orthonormal to the first two, it has to be in the  third dimension. 

### Linear combinations of orthonormal vectors
Suppose a vector $x$ is a linear combination of $a_1,...,a_k$, where  $a_1,...,a_k$ are *orthonormal*,
$$
x=\beta_1a_1+...+\beta_ka_k
$$
Taking the inner product of the left-hand and right-hand sides of this equation with $a_i$ yields
$$
a^T_ix=a^T_i(\beta_1a_1+...+\beta_ka_k)=B_i
$$
using the same argument as above. So if a vector x is a linear combination of orthonormal vectors, we can easily find the coefficients of the linear combination by taking the inner products with the vectors.


For any $x$ that is a linear combination of orthonormal vectors $a_1,...,a_k$ we have the identity
$$
x=(a^T_1x)a_1+...+(a^T_kx)a_k
$$
In the above the inner product on the RHS is the coefficients in the linear combination, for example $(a^T_1x)=\beta_1$.

> [!NOTE] *Orthonormal expansion formula*
> The equation above is sometimes called the *orthonormal expansion formula*; the right-hand side is called the *expansion* of $x$ in the basis $a_1,...,a_k$. It shows that any $n-$vector can
be expressed as a linear combination of the basis elements, with the coefficients given by taking the inner product of $x$ with the elements of the basis.


Example:
$x$ is a $3-$vector and 5.3 are orthonormal vectors 
![[SLIAL lecture-2, example of orthonormal vectors.png]]
Then to get the coefficients of that we multiply with the  linear combination to get  $x$
![[SLIAL lecture-2 rest of example of orthonormal vectors.png]]
____
## 5.4 Gram-Schmidt Algorithm

> [!NOTE] Video 
> Link: https://www.youtube.com/watch?v=IZhpqYeKZEM&list=PLoROMvodv4rMz-WbFQtNUsUElIh2cPmN9&index=16

Gram-Schmidt Algorithm is an algorithm that can be used to determine if a list of $n-$vectors $a_1,...,a_k$ is linearly independent.

**Describtion**
If the vectors are linearly independent, the Gram-Schmidt algorithm produces an orthonormal collection of vectors $q_1,...,q_k$ with the following properties: 
* For each $i = 1,...,k$, $a_i$ is a linear combination of $q_1,..., q_i$, and $q_i$ is a linear combination of $a_1,...,a_i$. 
* If the vectors $a_1,...,a_{j-1}$ are linearly independent, but $a_1,...,a_j$ are linearly dependent, the algorithm detects this and terminates. 
In other words, the Gram-Schmidt algorithm finds the first vector $a_j$ that is a linear combination of previous vectors $a_1,...,a_{j-1}$.
___
**Gram-Schmidt algorithm Pseudocode**
![[SLIAL Lecture-2 Gram-Schmidt algorithm Pseudocode.png]]
___
The orthogonalization step, with $i = 1$, reduces to $\tilde q_1 = a_1$. If the algorithm does not quit (in step 2), i.e., $\tilde q_1,...,\tilde q_k$ are all nonzero, we can conclude that the original collection of vectors is linearly independent; if the algorithm does quit early, say, with $\tilde q_j = 0$, we can conclude that the original collection of vectors is linearly dependent (and indeed, that $a_j$ is a linear combination of $a_1,.., a_{j-1}$).
![[SLIAL Lecture-2 Gram-Schmidt example.png]]