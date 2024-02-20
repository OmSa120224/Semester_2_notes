Date: 13/02/2024
Literature: Chapter 5
_____
# Chapter 5: Linear independence



## 5.1 Linear dependence

A collection or list of $n$-vectors $a_1,...,a_k$ (with k>1) is called *linearly dependent* if 
$$\beta_1 a_1+...+ \beta_k a_k=0 $$
hold for some $\beta_1,...,\beta_k$ ==that are NOT all zero==. In other words, we can form the zero vector as a linear combination of the vectors, with coefficients that are not all zero. Linear dependence of a list of vectors does not depend on the ordering of the vectors in the list

> [!NOTE]
> It must be remembered that linear dependence is an attribute of a collection of vectors, and not individual vectors.

The linear dependence can also be defined in the following way. If a collection of $n$-vectors $a_1,...,a_k$ is linearly depended, then at least one of the vectors can be expressed as a linear combination of the other vectors. 
$$
a_i={\beta_1 \over -\beta_i}a_1+...+{\beta_{i-1} \over -\beta_i}a_{i-1}+{\beta_{i+1} \over -\beta_i}a_{i+1}+...+{\beta_k \over -\beta_i}a_k
$$
#### Examples
* A list consisting of a single vector is linearly dependent only if the vector is zero, which also means that the scalar $\beta$ ==is cannot be zero(remember the definition)==
* A list of two $n$-vectors $a_1$ and $a_2$ is linearly dependent only if one $a_i$ is a multiple of the other (they are on the same line). For example  $$a_2=\alpha_1 a_1$$

### Linearly independent vectors.
Collection of $n$-vectors $a_1,..., a_k$ (with $k ≥ 1$) is called linearly independent if it is not linearly dependent, which means that
Equation 5.1
$$\beta_1 a_1+...+ \beta_k a_k=0 $$
only hold for $\beta_1=...=\beta_k=0$. In other words, the only linear combination of the vectors that equals the zero vector is the linear combination with all coefficients zero.

An equivalent definition is, for $n$-vectors  $a_1,..., a_k$, no $a_i$ can be expressed as a linear combination of the other vectors.

* Linear independence is an attribute of a collection of vectors, and not individual vectors.

#### Example
* The standard unit $n-vectors\; e_1,...,e_n$ are linearly independent. To see this, suppose that (5.1) holds. We have $$0= \beta_1e_1+,..,+\beta_ne_n= \left[\;\; \begin{matrix} \beta_1 \\.\\.\\.\\ \beta_n \end{matrix} \;\;\right] $$
* So we conclude that $\beta_1 =...=\beta_n=0$ 

### Linear combinations of linearly independent vectors
Suppose a vector x is a linear combination of linearly independent vectors $a_1,...,a_k$
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
If a collection of vectors is linearly dependent, then any superset of it is linearly dependent. In other words: If we add vectors to a linearly dependent collection of vectors, the new collection is also linearly dependent. Any nonempty subset of a linearly independent collection of vectors is linearly independent. In other words: Removing vectors from a collection of vectors preserves linear independence.


## 5.2 Basis


### Independence-dimension inequality
if the $n$-vectors $a_1,...,a_n$ are linearly independent then $k≤n$. 
* In other words A *linearly independent collection* of n-vectors can have at most n elements.
Put another way 
* Any *collection* of $n + 1$ or more $n$-vectors is *linearly dependent*.
Example 
![[Figure 5.1 independence-dimension.png]]

### Basis
A collection of $n$ linearly independent $n$-vectors (a collection of linearly independent vectors of the maximum size) is called *basis*. 

If the $n$-vectors $a_1,...,a_n$ are a basis, then any $n$-vector $b$ can be written as a linear combination of them. 

* Any $n$-vector $b$ can be written in a unique way as a linear combination of a *basis* $a_1,..., a_n$.

(own words might be wrong)
In a space of $n$ dimensions there can only be at most $n$ vectors that are independent. if we add another vectors $b$ to the space, then the collection of vectors is not independent anymore, is dependent. When a collection of vectors is dependent at least on of the vectors in the collection can be written as a combination of the other vectors.


Example:
The unit vectors 



### Proof of independence-dimension inequality







## 5.3 Orthonormal vectors
A collection of vectors $a_1,...,a_k$ is *orthogonal* or mutually orthogonal if $a_i \perp a_j$ for any $i,j$ with $i≠j,\;i,j=1,...,k$.

A collection of vectors $a_1,...,a_k$ is *orthonormal* if it is orthogonal and $||a_i||=i$ for $i=1,...,k$. 

(A vector of norm one is called *normalized*; dividing a vector by its norm is called *normalizing* it.)
Thus, each vector in an orthonormal collection of vectors is normalized, and two different vectors from the collection are orthogonal.
$$
a_i\,^Ta_j=  \{\begin{matrix}1\;\;\; i=j\\ 0\;\;\; i≠j \end{matrix}
$$
* Orthonormality, like linear dependence and independence, is an attribute of a collection of vectors, and not an attribute of vectors individually.


### Linear combinations of orthonormal vectors
Suppose a vector $x$ is a linear combination of $a_1,...,a_k$, where  $a_1,...,a_k$ are *orthonormal*,
$$
x=\beta_1a_1+...+\beta_ka_k
$$
Taking the inner product of the left-hand and right-hand sides of this equation
with $a_i$ yields
page 106




## 5.4 Gram-Schmidt Algorithm
re-read 
