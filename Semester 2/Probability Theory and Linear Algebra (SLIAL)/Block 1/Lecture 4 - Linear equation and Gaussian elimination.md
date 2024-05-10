**Scheduled**: 2024/02/20
**Latest Revision**: 2024/05/09
**Literature**: Introduction to Applied Linear Algebra: Vectors, Matrices, and Least Squares by S. Boyd and L. Vandenberghe.  **Chapter 8**. And Linear Algebra and Its Applications" by Lay, Lay, McDonald. **Chapters 1.1 & 1.2**. 
___
# Chapter 8 - Linear Equation

## 8.1 Linear and affine functions
### Vector-valued functions of vectors.
The notation $f : R^n \to R^m$ means that $f$ is a function that maps real $n-$vectors to real $m-$vectors. 

#### The matrix-vector product function.
Suppose A is an $m ⨉ n$ matrix. We can dene a function $f : R^n \to R^m$ by $f(x) = Ax$.

### Superposition and linearity.
The function $f : R^ n \to R^m$, dened by $f(x) = Ax$, is linear, i.e., it satisfies the superposition property:
Equation 8.1
$$f(\alpha x +\beta y) = \alpha f(x) +\beta f(y)  $$
holds for all $n-$vectors $x$ and $y$ and all scalars $\alpha$ and $\beta$ .

We can verify that superposition holds for $f$ using properties of matrix-vector and scalar-vector multiplication:
$$
\begin{matrix} f(\alpha x +\beta y) = A(\alpha x +\beta y) \\ \;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;=A(\alpha x) + A(\beta y) \\\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\; = \alpha (Ax) +\beta(Ay) \\\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\; = \alpha f(x) +\beta f(y)   \end{matrix}
$$
Thus we can associate with every matrix $A$ a linear function $f(x) = Ax$.

The converse is also true. Suppose f is a function that maps $n-$vectors to $m-$vectors, and is linear, i.e., (8.1) holds for all $n-$vectors $x$ and $y$ and all scalars $\alpha$ and $\beta$ . Then there exists an $m ⨉ n$ matrix $A$ such that $f(x) = Ax$ for all $x$. This can be shown by showing that if $f$ is linear, then
Equation 8.2
$$
f(x) = x_1f(e_1) + x_2f(e_2) +...+ x_nf(e_n);
$$
where $e_k$ is the $k_{th}$ unit vector of size $n$. The right-hand side can also be written as a matrix-vector product $Ax$, with
$$
A=[f(e_1)\;\; f(e_2)\;\; \dots \;\; f(e_n)]
$$

> [!NOTE] Note
> As in chapter 2.1 it is easily shown that the matrix-vector representation of a linear function is unique. If $f : R^n \to R^m$ is a linear function, then there exists exactly one matrix $A$ such that $f(x) = Ax$ for all $x$.

______
## 8.2 Linear function models
Many functions or relations between variables that arise in natural science, engineering, and social sciences can be approximated as linear or affine functions. In these cases we refer to the linear function relating the two sets of variables as a *model* or an *approximation*, to remind us that the relation is only an approximation, and not exact

### 8.2.1 Taylor approximation

### 8.2.2 Regression model

________
## 8.3 Systems of linear equations
Consider a set (also called a system) of m linear equations in $n$ variables or unknowns $x_1,...,  x_n$:
$$
\begin{matrix}A_{11}x_1 + A_{12}x_2+...+A_{1n} =b_1 \\
A_{21}x_1 + A_{22}x_2+...+A_{2n} =b_2\\ 
\vdots \\
A_{m1}x_1 + A_{m2}x_2+...+A_{mn} =b_m\end{matrix}
$$
The numbers $A_{ij}$ are called the *coefficients* in the linear equations, and the numbers $b_i$ are called the *right-hand sides*. These 

equations can be written succinctly in matrix notation as
$$
Ax=b
$$
In this context, the $m ⨉ n$ matrix $A$ is called the *coefficient matrix*, and the $m-$vector $b$ is called the *right-hand side*. An $n-$vector $x$ is called a solution of the linear equations if $Ax = b$ holds.

A set of linear equations can have no solutions, one solution, or multiple solutions.

**Example**
![[8.3 example.png]]

### Over-determined and under-determined systems of linear equations. 
The set of linear equations is called *over-determined* if $m > n$ (more row than columns), *under determined* if $m < n$ (more columns than rows), and square if $m = n$; these correspond to the coefficient matrix being tall, wide, and square, respectively. (NOTE: distinguish between the coefficients matrix and the augmented matrix. When talking of over- under-determined we mean the coefficients matrix)

When the system of linear equations is over-determined, there are more equations than variables or unknowns. When the system of linear equations is under-determined, there are more unknowns than equations. When the system of linear equations is square, the numbers of unknowns and equations is the same. 

A set of equations with zero right-hand side, $Ax = 0$, is called a *homogeneous* set of equations. Any homogeneous set of equations has $x = 0$ as a solution.


____

# Linear Algebra and Its Applications

## 1.1 SYSTEMS OF LINEAR EQUATIONS
A **linear equation** in the variables $x_1,..,x_n$ is an equation that can be written in the form (equation 1)
$$
a_1x_1+a_2x_2+...a_nx_n=b
$$
where $b$ and and the coefficients $a_1...a_n$ are real or complex numbers, usually known in advance. 

A solution of the system is a list $s_1, s_2,..., s_n$ of numbers that makes each equation a true statement when the values $s_1, s_2,..., s_n$ are substituted for $x_1, x_2,..., x_n$, respectively. 

* The set of all possible solutions is called the solution set of the linear system.
* two linear systems are called equivalent if they have the same solution set. That is, each solution of the first system is a solution of the second system, and each solution of the second system is a solution of the first

> [!NOTE]
> A system of linear equations has
> 1. no solution, or
> 2. exactly one solution, or
> 3. infinitely many solutions.
>    
>A system of linear equations is said to be *consistent* if it has either one solution or infinitely many solutions; a system is *inconsistent* if it has no solution

_____
### Matrix Notation
The essential information of a linear system can be recorded compactly in a matrix. Given the system below
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
An augmented matrix of a system consists of the coefficient matrix with an added column containing the constants from the right sides of the equations.
_____
#### Solving a Linear System
Three basic operations are used to simplify a linear system: 

> [!NOTE] Elementary Row operations
>  - **Replacement**: Replace one equation by the sum of itself and a  multiple of another equation 
> - **Interchange** : Interchange two rows.
> - **Scaling**: Multiply all the terms in an equation by a nonzero constant

> [!NOTE] NOTE
> If the augmented matrices of two linear systems are row equivalent, then the two systems have the same solution set.

_____
#### Existence and Uniqueness Questions

> [!NOTE] TWO Fundamental Questions About A Linear System
> 1. Is the system consistent; that is, does at least one solution *exist*?
> 2. If a solution exists, is it the *only* one; that is, is the solution *unique*?

_____
## 1.2 ROW REDUCTION AND ECHELON FORMS


> [!NOTE] Definition: Echelon form(or Row Echelon form) 
> A rectangular matrix is in *echelon form* if it has the following three properties. 
> 1. All nonzero rows are above any rows of all zeros.
> 2. Each leading entry of a row is in a column to the right of the leading entry of the row above.
> 3. All entries in a column below a leading entry are zeros.
>    
> If a matrix in echelon form satisfies the following additional conditions, then it is in *reduced echelon form* (or *reduced row echelon form*):
> 4. The leading entry in each nonzero row is 1.
> 5. Each leading 1 is the only nonzero entry in its column.

The triangular matrices below are in echelon form and reduced echelon form respectively. 
![[SLIAL Lecture 4 Echelon and reduced Echelon form examples.png]]

Any nonzero matrix may be *row reduced* (that is, transformed by elementary row operations) into more than one matrix in echelon form, using different sequences of row operations. However, the reduced echelon form one obtains from a matrix is unique. Hence we have the following theorem:

> [!NOTE] Theorem 1: Uniqueness of the Reduced Echelon Form
> Each matrix is row equivalent to one and only one reduced echelon matrix.

______
#### Pivot Positions

> [!NOTE] Definition: Pivot Position
> A *pivot position* in a matrix $A$ is a location in $A$ that corresponds to a leading 1 in the reduced echelon form of $A$. A pivot column is a column of $A$ that contains a pivot position.

**Example**:
The following matrices are in echelon form. The leading entries ($\blacksquare$) 
may have any nonzero value; the starred entries ($*$) may have any value (including zero). Here squares ($\blacksquare$) identify the pivot positions.
![[SLIAL Lecture 4 - example 1 of echelon  form.png]]
The following matrices are in reduced echelon form because the leading entries are 1’s, and there are 0’s below and above each leading 1.
![[SLIAL Lecture 4 reduced echelon form.png]]
______
### The Row Reduction Algorithm

> [!NOTE] Step 1
> Begin with the leftmost nonzero column. This is a pivot column. The pivot position is at the top.


> [!NOTE] Step 2
> Select a nonzero entry in the pivot column as a pivot. If necessary, interchange rows to move this entry into the pivot position


> [!NOTE] Step 3
> Use row replacement operations to create zeros in all positions below the pivot.


> [!NOTE] Step 4
> Cover (or ignore) the row containing the pivot position and cover all rows, if any, above it. Apply steps 1–3 to the submatrix that remains. Repeat the process until there are no more nonzero rows to modify


> [!NOTE] Step 5
> Beginning with the rightmost pivot and working upward and to the left, create zeros above each pivot. If a pivot is not 1, make it 1 by a scaling operation

____
### Solutions of Linear Systems
The row reduction algorithm leads directly to an explicit description of the solution set of a linear system when the algorithm is applied to the augmented matrix of the system.


$$
\begin{bmatrix}1\ \ \ 0\ -5 \ \ \ 1 \\ 0 \ \ \ 1 \ \ \ 1 \ \ \ 4 \\ 0 \ \ \ 0\ \ \ 0\ \ \ 0 \end{bmatrix}
$$
There are three variables because the augmented matrix has four columns. The associated system of equations is
$$
\begin{matrix}x_1 \ \ \ \ \  -5x_3=1\\ \ \ \ \ x_2+x_3=4\\ \ \ \ \ \ \ 0=0 \end{matrix}
$$
The variables $x_1$ and $x_2$ corresponding to pivot columns in the matrix are called basic variables.  The other variable, $x_3$, is called a free variable.

$$
\begin{cases}x_1=1+5x_3\\ x_2=4-x_3\\ x_3\;\; is\;\; free \end{cases}
$$
The statement “$x3\;\; is\;\; free$” means that you are free to choose any value for $x_3$.


> [!NOTE] Note
> Each different choice of $x_3$ determines a (different) solution of the system, and every solution of the system is determined by a choice of $x_3$.

____
### Parametric Descriptions of Solution Sets
**Pivot Variables**: These are variables corresponding to the leading entries (pivots) in the augmented matrix obtained after applying Gaussian elimination (or a similar method) to the system of equations. The values of pivot variables are determined by other variables in the system.

**Free Variables**: These are variables that are not pivot variables. They are left unconstrained and can take any value. The values of free variables are typically expressed in terms of parameters.

Whenever a system is inconsistent, the solution set is empty, even when the system has free variables. In this case, the solution set has no parametric representation

___

### Back-Substitution
Back substitution is a method used to solve systems of linear equations, particularly those that have been reduced to upper triangular or row-echelon form. It's typically the final step in Gaussian elimination.

Here's how back substitution works:

1. **Start from the bottom equation**: In a system of linear equations reduced to upper triangular or row-echelon form, the last equation often only contains one variable and one constant term. You can directly solve for this variable.
    
2. **Substitute the solution into the second-to-last equation**: Once you've found the value of the variable from the last equation, you can substitute it back into the second-to-last equation and solve for the corresponding variable.
    
3. **Repeat this process**: Continue substituting the values of variables that you've found back into the equations above until you've solved for all the variables.

When solving a system by hand, the best method is reduced echelon form, as it has the leas likelihood for making error, computers on the other hand uses back substitution. 
_____
### Existence and Uniqueness Questions

![[Uniqueness answer.png]]
When there exist free variable the solution would not be unique as each choice of  the unique variable will result an a different solution.


> [!NOTE] Theorem 2: Existence of Uniqueness Theorem
> A linear system is consistent if and only if the rightmost column of the augmented matrix is *not* a pivot column—that is, if and only if an echelon form of the augmented matrix has no row of the form $$ [0\;\;\;...\;\;\;0\;\;b]$$
If a linear system is consistent, then the solution set contains either (i) a unique solution, when there are no free variables, or (ii) infinitely many solutions, when there is at least one free variable.

![[Using Row reduction to solve a linear system.png]]
_______
