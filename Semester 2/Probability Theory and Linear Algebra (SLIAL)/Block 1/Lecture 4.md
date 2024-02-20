Date: 20/02/2024
Literature: Chapter 8 &  Linear Algebra and Its Applications
___
# Chapter 8 - Linear Equation

## 8.1 Linear and affine functions
### Vector-valued functions of vectors.
The notation $f : R^n \to R^m$ means that $f$ is a function that maps real n-vectors to real m-vectors.


### The matrix-vector product function.
Equation 8.1
$$f(\alpha x +\beta y) = \alpha f(x) +\beta f(y)  $$

Equation 8.2
$$
f(x) = x_1f(e_1) + x_2f(e_2) +...+ x_nf(e_n);
$$

## 8.2 Linear function models
Many functions or relations between variables that arise in natural science, engineering, and social sciences can be approximated as linear or affine functions. In these cases we refer to the linear function relating the two sets of variables as a *model* or an *approximation*, to remind us that the relation is only an approximation, and not exact

### 8.2.1 Taylor approximation
did not understand



## 8.3 Systems of linear equations
![[8.3 example.png]]

### Over-determined and under-determined systems of linear equations. 
The set of linear equations is called over-determined if m > n, under determined if m < n, and square if m = n; these correspond to the coefficient matrix being tall, wide, and square, respectively. When the system of linear equations is over-determined, there are more equations than variables or unknowns. When the system of linear
equations is under-determined, there are more unknowns than equations. When the system of linear equations is square, the numbers of unknowns and equations is the same. A set of equations with zero right-hand side, $Ax = 0$, is called a homogeneous set of equations. Any homogeneous set of equations has $x = 0$ as a solution.


____

# Linear Algebra and Its Applications

## 1.1 SYSTEMS OF LINEAR EQUATIONS
A **linear equation** in the variables $x_1,..,x_n$ is an equation that can be written in the form (equation 1)
$$
a_1x_1+a_2x_2+...a_nx_n=b
$$
where $b$ and and the coefficients $a_1...a_n$ are real or complex numbers, usually known in advance. 


* The set of all possible solutions is called the solution set of the linear system.
* two linear systems are called equivalent if they have the same solution set. That is, each solution of the first system is a solution of the second system, and each solution of the second system is a solution of the first

A system of linear equations has
1. no solution, or
2. exactly one solution, or
3. infinitely many solutions.
A system of linear equations is said to be **consistent** if it has either one solution or infinitely many solutions; a system is **inconsistent** if it has no solution.

### Matrix Notation
given the system below
$$
\begin{matrix}
x_1 -2x_2+x_3=8 \\
2x_2-8x_3=8 \\
5x_1-5x=10
\end{matrix}
$$
it can be rewritten as follow, which is called **coefficient matrix**
$$
\begin{bmatrix}
1&-2&1\\
0&2&-8\\
5&0&-5
\end{bmatrix}
$$
The **augmented matrix** of the system could be written as follows
$$
\begin{bmatrix}
1&-2&1&0\\
0&2&-8&8\\
5&0&-5&10
\end{bmatrix}
$$

#### Solving a Linear System
Three basic operations are used to simplify a linear system: 
* Replace one equation by the sum of itself and a multiple of another equation 
* Interchange two equations
* Multiply all the terms in an equation by a nonzero constant



> [!NOTE] Title
> If the augmented matrices of two linear systems are row equivalent, then the two systems have the same solution set.


#### Existence and Uniqueness Questions
The Fundamental Questions About A Linear System
1. Is the system consistent; that is, does at least one solution exist?
2. If a solution exists, is it the only one; that is, is the solution unique?

## 1.2 ROW REDUCTION AND ECHELON FORMS
![[Echelon forms.png]]

Any nonzero matrix may be row reduced (that is, transformed by elementary row operations) into more than one matrix in echelon form, using different sequences of row operations. However, the reduced echelon form one obtains from a matrix is unique. 

> [!NOTE] Theorem: Uniqueness of the Reduced Echelon Form
> Each matrix is row equivalent to one and only one reduced echelon matrix.

#### Pivot Positions

> [!NOTE] Deffinition: Pivot possition
> A pivot position in a matrix A is a location in A that corresponds to a leading 1 in the reduced echelon form of A. A pivot column is a column of A that contains a pivot position.


#### Solutions of Linear Systems


#### Existence and Uniqueness Questions

![[Uniqueness answer.png]]
When there exist free variable the solution would not be unique as each choice of  the unique variable will result an a different solution.


> [!NOTE] Theorem: Existence of Uniqueness Theorem
> A linear system is consistent if and only if the rightmost column of the augmented matrix is not a pivot column—that is, if and only if an echelon form of the augmented matrix has no row of the form $$ [0\;\;\;...\;\;\;0\;\;b]$$
If a linear system is consistent, then the solution set contains either (i) a unique solution, when there are no free variables, or (ii) infinitely many solutions, when there is at least one free variable.

![[Using Row reduction to solve a linear system.png]]