Date: 06/02/2024
Literature: Chapter 1 + 2.1
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
* Zero vector, and its size
* Unit vectors and its size and  notation
* Ones vector
* Sparsity

## 1.2 Vector addition
Two vectors *of the same size* can be added together by adding the corresponding elements, to form another vector of the same size.
$$
\begin{bmatrix} 0 \\ 7\\ 3 \end{bmatrix} + \begin{bmatrix} 1 \\ 2\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\ 9\\ 3 \end{bmatrix}
$$
subtraction
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
* Distributive: $(\beta + \gamma) \vec a = \vec a \beta + \vec a \gamma$
* Another version of Distributive: $(\vec a + \vec b) \beta= \vec a \beta + \vec b \beta$



**Important terms to understand and remember(check the book p. 27)**
* *Linear combinations*: 
* *Linear combination of unit vectors*: We can write any $n-vector \:\:b$ as a linear combination of the standard unit vectors.
* *Special linear combinations*: 

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

General Examples of the dot product:
![[General Examples of the dot product.png]]


## 1.5 Complexity of vector computations


_____
# Chapter 2: Linear Function

## 2.1 Linear Functions

**Function notation.**
read again 

**The inner product function.**
read again 

**Superposition and linearity**
A function that satisfies the superposition property is called linear.
The superposition equality
$$
f(\alpha \vec x + \beta \vec y) = \alpha f(\vec x) + \beta f(\vec y)
$$
This equality could be broken down into two  properties. 
* *Homogeneity*: $f(\alpha \vec x) = \alpha f(\vec x)$
* *Additivity*: $f(\vec x+ \vec y)= f(\vec x) + f(\vec y)$
*Homogeneity* states that scaling the (vector) argument is the same as scaling the function value; *additivity* says that adding (vector) arguments is the same as adding the function values.



**Inner product representation of a linear function** 
read again 

