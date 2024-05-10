**Scheduled**: 2024/02/06
**Latest Revision**: 2024/05/02
**Literature**: Introduction to Applied Linear Algebra: Vectors, Matrices, and Least Squares by S. Boyd and L. Vandenberghe.  **Chapter 1 & 2.1**
____
# Chapter 1: Vectors

## 1.1 Vectors
A *vector* is an ordered finite list of numbers. Vectors are usually written as vertical arrays, surrounded by square or curved brackets, as in
$$
\begin{pmatrix}
-1.1\\
0.0\\
3.2
\end{pmatrix}
$$
$$
\begin{bmatrix}
-1.1\\
0.0\\
3.2
\end{bmatrix}
$$
They can also be written as numbers separated by commas and surrounded by parentheses.
$$(-1.1, 0.0, 3.2)$$
* The *elements* (or *entries*, *coefficients*, *components*) of a vector are the values in the array.
* The *size* (also called *dimension* or *length*) of the vector is the number of elements it contains.
* A vector of size *n* is called an *n-vector*.
* A *1-vector* is considered to be the  same as a number (1.3 is same as \[1.3\]).
* Two vectors $a$ and $b$ are equal, which we denote $a = b$, if they have the same size, and each of the corresponding entries is the same.
* The numbers or values of the elements in a vector are called *scalars*.
* The set of all real $n-vectors$ is denoted $R^n$.

**Block or stacked vectors**: It is sometimes useful to define vectors by *concatenating* or stacking two or more vectors, as in(or any of the other two notation)
$$
a=\begin{bmatrix}
b\\ c\\ d
\end{bmatrix}
$$

Where $a, b, c$  and $d$ are vectors.
If $b$ is an $m-vector$, $c$ is an $n-vector$, and $d$ is a $p-vector$, this defines the $(m + n + p)-vector$.
$$
a = (b_1, b_2,..., b_m, c_1, c_2, ..., c_n, d_1, d_2,..., d_p):
$$

**Subvectors**: $b,c$ and $d$ are called *subvecrtors* or *slices*. the following notation is called *index range*
$$
a_{r:s}=(a_r,...,a_s)
$$

> [!warning] Indexing 
> The range of the index. In many computer languages, arrays of length $n$ are indexed from $i = 0$ to $i = n-1$. But in standard mathematical notation, $n-vectors$ are indexed from $i = 1$ to $i = n$.

**Important terms to understand and remember(check the book p. 14)**
* Zero vector, and its size: A zero vector is a vector with all elements equal to zero
* Unit vectors and its size and  notation: A (standard) unit vector is a vector with all elements equal to zero, except one element which is equal to one
* Ones vector
* Sparsity

## 1.2 Vector addition
Two vectors *of the same size* can be added together by adding the corresponding elements, to form another vector of the same size.
$$
\begin{bmatrix} 0 \\ 7\\ 3 \end{bmatrix} + \begin{bmatrix} 1 \\ 2\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\ 9\\ 3 \end{bmatrix}
$$
Subtraction
$$
\begin{bmatrix} 0 \\ 7\\ 3 \end{bmatrix} - \begin{bmatrix} 1 \\ 2\\ 0 \end{bmatrix} = \begin{bmatrix} -1 \\ 5\\ -3 \end{bmatrix}
$$

**Properties of vector addition and subtraction**
* Vector addition is *commutative*: $\vec a + \vec b = \vec b + \vec a$
* Vector addition is *associative*: *$( \vec a + \vec b) + \vec c = \vec a + (\vec b + \vec c) = \vec a + \vec b + \vec c$
* Adding the *zero vector* has no effect: $\vec a + \vec 0 = \vec 0 + \vec a = \vec a$.
* Subtracting a vector from it self yield to a *zero vector*: $\vec a- \vec a=\vec 0$


## 1.3 Scalar-vector multiplication
Scalar multiplication *or scalar-vector multiplication*, in which
a vector is multiplied by a scalar (i.e., number), which is done by multiplying every element of the vector by the scalar.
$$
(-2)\begin{bmatrix} 1\\ 9\\ 6 \end{bmatrix} = \begin{bmatrix} -2\\ -18\\ -12 \end{bmatrix} 
$$

**Properties of *Scalar-vector multiplication**
* *Commutative*: $\vec a \beta = \beta \vec a$
* *Associative*: $(\vec a \beta) \gamma = \vec a (\beta \gamma)$ 
* *Left Distributive*: $(\beta + \gamma) \vec a = \vec a \beta + \vec a \gamma$
* *Right Distributive*: $(\vec a + \vec b) \beta= \vec a \beta + \vec b \beta$

**Important terms to understand and remember(check the book p. 27)**
* ***Linear combinations**: 
Linear combinations. If $a_1,...,a_n$ am are *n-vectors*, and $\beta_1,...\beta_n$ are scalars, the n-vector
$$
a_1\beta_1+...+a_n\beta_n
$$

is called a linear combination of the vectors  $a_1,...,a_n$. The  scalars  
$\beta_1,...\beta_n$  are called the coefficients of the linear combination.

* *Linear combination of unit vectors*: We can write any $n-vector \:\:b$ as a linear combination of the standard unit vectors.
We can write any $n-vector$ $b$ as a linear combination of the standard unit vectors, as
$$
b=b_1e_1+...+b_ne_n
$$
### Special linear combinations.
- Sum of the vectors
Let $a_1,...,a_n$ be $n-vectors$ and $\beta_1=...=\beta_m=1$ be scalars, then the linear combinations of them is the sum of the vectors.

- The average of the vectors
Let $a_1,...,a_m$ be n vector and $\beta_1=...=\beta_m=1/m$ then the linear combination of them is the average 

- Weighted average
Let $a_1,...,a_n$ be $n-vectors$ and let  $\beta_1+...+\beta_m=1$ then the combination of them is a weighted average which add up to 100%.

_____
## 1.4 Inner Product or Dot product

The (standard) *inner product* (also called *dot product*) of two *n-vectors* is defined as the scalar
$$
\vec a^T\vec b = \vec a_1 \vec b_1+ \vec a_2 \vec b_2+,...,+ \vec a_n \vec b_n  
$$
Other notations for the Inner product:
$$ 
\langle a, b \rangle \:\: or \:\: \langle a | b \rangle \:\: or \:\: (a,b) \:\: or \:\: a \cdot b
$$
**Properties**
* *Commutative*: $\vec a^T \vec b = \vec b ^T \vec a$
* *Associativity with scalar multiplication*: $(\gamma \vec a)^T \vec b = \gamma (\vec a ^T \vec b) = \gamma \vec a^T \vec b$
* *Distributivity with vector addition*: $(\vec a + \vec b)^T \vec c = \vec a ^T \vec c + \vec b^T \vec c$


**Inner product and orthogonality**: Two vectors are orthogonal to each other if their inner product is zero.

General Examples of the dot product:
![[General Examples of the dot product.png]]

## 1.5 Complexity of vector computations
![[1.5 complexity of simply vector operations.png]]
The complexity of inner product when one of the two vectors is sparse, is approximately about 2 times the number of non-zero entries $nnz(x)$ in the sparse vector.  
_____
# Chapter 2: Linear Function

## 2.1 Linear Functions

### **Function notation.**
$$
f:R^n \to R
$$
means that $f$ is a function that takes an $n-vectors$ in  and gives out a number.

### **The inner product function.**
read again 
$$f(x) = a^Tx = a_1x_1 + a_2x_2 +...+ a_nx_n$$
#### **Superposition and linearity**
A function that satisfies the superposition property is called ***linear***.
The superposition equality
$$
f(\alpha \vec x + \beta \vec y) = \alpha f(\vec x) + \beta f(\vec y)
$$
if a function is linear then the identity holds for all $\alpha$ and $\beta$ and all $x$ and $y$.

This equality could be broken down into two properties. 
* *Homogeneity*: $f(\alpha \vec x) = \alpha f(\vec x)$
Homogeneity states that scaling the (vector) argument is the same as scaling the function value; 
* *Additivity*: $f(\vec x+ \vec y)= f(\vec x) + f(\vec y)$
*Additivity* says that adding (vector) arguments is the same as adding the function values.

#### The inner product function
$a$ is an $n-vector$, then the function 
$$
f(x)=a^Tx=a_1x_1+...+a_nx_n
$$
the above inner product function turns out to be linear because
we know from the superposition equality that a function is linear if 
$$
f(\alpha x+\beta y)= \alpha f( x) + \beta f( y)
$$
however we can rewrite the RHS using the inner product 
$$
f(\alpha x+\beta y)= a^T(\alpha x+\beta y)
$$
then by applying some properties of the inner product
$$
\begin{matrix}
f(\alpha x+\beta y)= a^T(\alpha x+\beta y) \cr
=a^T(\alpha x)+a^T(\beta y) \cr
=\alpha(a^Tx)+\beta(a^Ty) \cr
=\alpha f(x)+\beta f(y)
\end {matrix}
$$

> [!NOTE] inner product and linear function
> It turns out any linear function $f(x)$ can be expressed as an inner product between $x$ and some vector $a$   meaning  $f(x)=a^Tx$


**Inner product representation of a linear function** 
suppose $f:R^n \to R$ is linear then it can be expressed as $f(x)=a^Tx$ for some $a$. Meaning  all linear functions can be expressed as an inner product.

Here one have to be specific about what the vectors $a$ is
$$a_i=f(e_i)$$
the $i_{th}$ entry of the vector $a$ is the function $f$ of the $i_{th}$ unit vector .
hence: 
$$
f(x)=f(x_1e_1+x_2e_2+...+x_ne_n)
$$
the above is saying that $f(x)$ is the same as function $f$ of ***the linear combination*** or the sum of vectors-scalar multiplication. Where one multiplies the $i_{th}$ entry of $x$ (the ...) by the $i_{th}$ unit vector (the vector)  which will give the vectors $x$ is we sums them up.

however if we use superposition role we get the following
$$
\begin{matrix}
f(x)=f(x_1e_1+x_2e_2+...+x_ne_n) \cr \cr
=x_1f(e_1)+x_2f(e2)+...+x_nf(e_n) \cr \cr
=a^Tx
\end{matrix}
$$
the above is saying that $f$ of a linear combination (first line) is the same as the linear combination of $f$ applied to each of the unit vectors (second line). Which is exactly the same as the inner product between $a$ and $x$ (third line) where $a$ is the vectors whose entries are $f(e_i)$

**NOTE:**
If a function is linear $f(x)=a^Tx$ then one can immediately calculate $f(\vec 0)=0$. Meaning a linear function has to go through the origin point.

#### Affine functions
General form 
$$
f(x)=a^Tx+b
$$
where $a$ and $x$ are $n-vectors$ and $b$ is a scalar.  Hence, $f(\vec 0)=b$

A function $f:R^n\to R$ is affine if and only if
$$
f(\alpha x+\beta y)= \alpha f( x) + \beta f( y)
$$
hold  all $n-vectors$ $x,y$ and for a restricted set of  $\alpha, \beta$ specifically  $\alpha+\beta=1$.

**NOTE**: that $\alpha$ or $\beta$ can be negative as long then add up to one. 


> [!warning] Note
> Affine functions are NOT the same as  linear function, because a linear function must go through the origin.
![[affine versus linear function.png]]

#### Taylor approximation
watch again
https://www.youtube.com/watch?v=H0jR5nqueWk&list=PLoROMvodv4rMz-WbFQtNUsUElIh2cPmN9&index=8

#### Regression Model


_____
## **Exercises:**


- Linear combinations: **1.18**
- Linear functions: **2.1**, **2.4**
- Affine functions: **2.2**, 2.7
- Regression models: **2.10**, 2.12
- Polynomials: 2.8



### Block-vectors: 
#### 1.4
![[Exercise 1.4.png]]
**(a) Use vector notation to express $w$ in terms of $d$.**
vector $w$ can be written as a block vector consisting of 7 $d$ vectors. 
$$
w=\begin{pmatrix} d_1\cr \vdots \cr d_7 \end{pmatrix}
$$
note that $d_1=d_2=...=d_7$

**(b) Use vector notation to express *d* in terms of *w*.**
there are multiple solutions for this, below are two of them
$$
d_1=w_{1:24}\;\; or \;\; d_2=w_{25:48}
$$
____
### Basic vector notation and operations: 
- **1.6**, **1.7**, 1.10, 1.11, 1.13
#### 1.6
![[Exercise 1.6.png]]
the $n-1$ vector $d$ is the difference between the following two vectors 
$$
d=\begin{pmatrix} x_2 \cr \vdots \cr x_n \end{pmatrix}-\begin{pmatrix} x_1 \cr \vdots \cr x_{n-1} \end{pmatrix}
$$
we can use slicing notation to represent $d$
$$
d=x_{2:n}-x_{1:n-1}
$$
#### **1.7**
![[exercise 1.7.png]]
$x$ uses entries 0 and 1. 
$y$ use entries -1 and 1

Express $y$ in terms of $x$
when $x$ is 1, $y$ is 1
so initially we  can say that 
$$
y=x
$$
however when $x$ is 0, $y$ is -1. Therefore
$$
y=2x-\vec1
$$

Express $x$ in terms of $y$
we just solve for $x$ in the equation we found above
$$
x=(y+ \vec1)/2
$$

___
#### Linear combinations: **1.18**
![[exercise 1.18.png]]
$$
\begin{matrix} 
b_1=\beta_1a_1+\beta_2 a_2 \cr 
b_2 =\beta_3a_1 +\beta_4a_2
\end{matrix}
$$
then $c$ is 
$$
c=\alpha_1 b_1 + \alpha_2b_2
$$
replacing $b_1$ and $b_2$
$$
\begin{matrix} c=\alpha_1(\beta_1a_1+\beta_2a_2)+\alpha_2(\beta_3a_1+\beta_4a_2) \cr
opening\; the \;brackets \cr
c=\alpha_1\beta_1a_1+\alpha_1\beta_2a_2+\alpha_2\beta_3a_1+\alpha_2\beta_4a_2 \cr
we \; can\; take\; common factors \; out\; which \; are \; a_1 \; and \; a_2 \cr
c=a_1(\alpha_1\beta_1+\alpha_2\beta_3)+a_2(\alpha_1\beta_2+\alpha_2\beta_4)



\end{matrix}
$$
___
### Linear functions: 
#### **2.1
![[exercise 2.1.png]]
a) choose the following
$$
z = \begin{pmatrix}
1 \cr 0
\end{pmatrix},\;\; y= \begin{pmatrix}
0 \cr 1
\end{pmatrix},\;\; \alpha=\beta=1/2
$$
then
$$
\alpha z+\beta y=1/2 \begin{pmatrix}
1 \cr 0
\end{pmatrix}+1/2 \begin{pmatrix}
0 \cr 1
\end{pmatrix}=\begin{pmatrix}
1/2 \cr 1/2
\end{pmatrix}
$$
$$
f(\alpha z+\beta y)=1/2-1/2=0
$$
however
$$
f(z)= max_k​z_k​−min_k​z_k​=max(1,0)−min(1,0)=1−0=1
$$
$$
f(y)=max_k​y_k​−min_k​y_k​=max(0,1)−min(0,1)=1−0=1
$$
now  we can see that 
$$
f(\alpha z+\beta y)= 0 ≠\alpha f(z)+\beta f(y)=1
$$
hence the function is not linear.

b)
a function is linear if it can be written as $f(x)=a^Tx$
choose $a=\begin{pmatrix}-1\cr 0 \cr \vdots \cr 0 \cr 1 \end{pmatrix}$

hence the function linear.

c)

#### 2.4