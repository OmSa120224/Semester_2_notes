Self-Study (w/o help)
**Scheduled**: 2024/02/09
**Latest Revision**: 2024/05/02
**Literature**: Introduction to Applied Linear Algebra: Vectors, Matrices, and Least Squares by S. Boyd and L. Vandenberghe.  **Chapter 3**.
_____
# Chapter 3: Norm and Distance
___
## 3.1 Norm

The $Euclidean\;norm$ of an $n-vector$ is the squareroot of the sum of the squares of its elements.
$$
||x|| = \sqrt{x^2_1 + x^2_2 + ... + x^2_n}
$$
The $Euclidean\; norm$ could also be expresses as the squareroot of the inner product of the vector with it self
$$
||x|| = \sqrt{x^Tx}
$$
Other terms for the $Euclidean\; norm$ are the $magnitude$ or the $length$ of the vector.

> [!warning] 
> Avoid length as it also refers to the dimension of the vector.

The norm is considered an extension of the absolute value or magnitude, that applies to vector.  

A vector is $small$ if its norm is small number and is $large$ if its norm is a large number (large and small depend on the context).

### **Properties of norm**
* $Nonnegative\; homogeneity$. $$|| \beta \vec x|| = | \beta |\: || \vec x ||$$Multiplying a vector by a scalar multiplies the norm by the absolute value of the scalar.
* $Triangle\; Inequality$. $$|| \vec x + \vec y|| ≤ ||\vec x||+||\vec y||$$ The norm of a sum of two vectors is no more than the sum of theirs norms. Also called *subadditivity*.
* $Nonnegativity$. $$||\vec x||≥0 $$$Definiteness$. $||\vec x|| = 0$ only if $\vec x =0$


### **Root-mean-square**
$$rms(\vec x)= \sqrt{{x^2_1+...+x^2_n \over n}} = {||\vec x|| \over \sqrt{n}}$$
Hint: If all the entries of a vector are the same, say, $\alpha$, then the RMS value of the vector is $|\alpha |$.
### **Norm of a sum**
Equation 3.1
$$||\vec x + \vec y|| = \sqrt{||x||^2 + 2 \vec x ^T \vec y + ||\vec y|| ^2}$$

### Norm of block of vectors
The norm squared of a stacked vectors is the sum of the norm-squared values if its subvectors.
For example, block vector $d = (a, b, c)$ (where a, b, and c are vectors), we have
$$||\vec d^2||= \vec d\ ^T \vec d = \vec a\ ^T \vec a + \vec b\ ^T \vec b+ \vec c\ ^T \vec c = ||\vec a ||^2 +||\vec b||^2 + ||\vec c||^2$$

This idea is often used in reverse 
$$||(\vec a, \vec b, \vec c)||= \sqrt{||\vec a ||^2 +||\vec b||^2 + ||\vec c||^2}= ||(||\vec a||, ||\vec b||, ||\vec c||)|| $$
The norm of a stacked vector is the norm of the vector formed from the norms of the subvectors. 

> [!warning]
> The RHS of the equation should be carefully read. The outer norm symbols enclose a 3-vector, with a (scalar) entries $||\vec a||,\ ||\vec b||$ and $||\vec c||$.

### Chebyshev inequality
Suppose that $x$ is an $n-vector$, and that $k$ of its entries satisfy $|x| ≥ a$, where $a > 0$. Then $k$ of its entries satisfy $x^2_i≥a^2$. It follows that
$$||x||^2 = x_1^2+x_2^2+...+x_n^2≥ka^2$$
We can conclude that $k≤{||x||^2 \over a^2}$, which is called the *Chebyshev*
*inequality*. 
- For ${||x||^2 \over a^2} ≥ n$, the inequality tells us nothing since we have always $k≤n$.
- For $a>||x||$, the inequality is $k≤{||x||^2 \over a^2} <1$, so we conclude that $k = 0$ (since $k$ is an integer). In other words, no entry of a vector can be larger in magnitude than the norm of the vector.
- In other cases it limits the number of entries in a vector that can be large.

The Chebyshev inequality is easier to interpret in terms of the *RMS* value of a vector. We can write it as
Equation 3.2
$${k \over n} = ({rms(x) \over a})^2 $$
did not understand this well, re-read page 57.
____
## 3.2 Distance
### Euclidean distance 
The norm can be used to define the $Eculidean\; distance$ between two vectors $\vec a$ and $\vec  b$ as the norm of their difference. 
$$dist(\vec a,\vec b)=||\vec a - \vec b||$$
For one, two, and three dimensions, this distance is exactly the usual distance between points with coordinates $\vec a$ and $\vec b$. But the Euclidean distance is defined for vectors of any dimension; we can refer to the distance between two vectors of dimension 100. 
![[Figure 3.1 The norm of the displacement a-b.png]]
When the distance between two $n$-vectors $\vec x$ and $\vec y$ is small we say they are '$close$' or '$nearby$', and when the distance $||\vec x - \vec y||$ is large, we say they are '$far$' (close and far depend on the context). 

### Triangle inequality
$$|| \vec x + \vec y|| ≤ ||\vec x||+||\vec y||$$
![[Figure 3.2 Triangle inequality.png]]
Consider a triangle in two or three dimensions, whose vertices have coordinates $a,\ b$ and $c$. The length of the sides are the distance between the vertices.
- $dist(a,\ b) = ||a -b||$
- $dist(b,\ c) = ||b-c||$
- $dist(a,\ c)= || a-c||$
The length of any side in the triangle cannot exceed the sum of the lengths of the other two.
Equation 3.3
$$
||a-c|| \leq ||a-b||+||b-c||
$$
This follows from the triangle inequality, since
$$
||a-c||=||(a-b)+(b-c)|| \leq ||a-b||+||b-c||
$$

### Unit of heterogeneous vector entries
The square of the distance between two $n$-vectors $\vec x$ and $\vec y$ is given by sum of the squares of the differences between their respective entries.
$$
||\vec x- \vec y||^2 = (x_1-y_1)^2+...+(x_n-y_n)^2
$$

> [!warning] Choice of units
> If a vector represent different types of features, say house area and numbers of bedrooms, the unit of which we give these quantities matter. If the numerical value of some features is much larger than the others, that feature will play a more significant role in the square of the norm. For example giving the area in thousand square feet versus giving the area in square feet.  Read page 61. 

___
## 3.3 Standard deviation
The standard deviation of an $n-vector$ $x$ is defined as the *RMS* value of the de-meaned vector $\vec x-avg(\vec x)\vec1$.
$$
std(x)=\sqrt{{(x_1-avg(x))^2+...+(x_n -ang(x))^2 \over n}}
$$
The standard deviation It can be written using the inner product and norm as Equation 3.4
$$
std(x)={||x-(\vec 1 ^T x/n)\vec 1)|| \over \sqrt n}
$$

> [!NOTE] Standard Deviation
> The standard deviation of a vector $x$ tells us the typical amount by which its entries deviate from their average value. The standard deviation of a vector is zero only when all its entries are equal.

In some applications the Greek letter $\sigma$  (sigma) is traditionally used to denote standard deviation, while the mean is denoted $\mu$  (mu). Using this notation we have, for an $n-vector \;x$,
$$\mu = \vec 1 ^T x /n $$
$$
\sigma = {||x- \mu *\vec1|| \over \sqrt n}
$$
### Average, RMS value, and standard deviation.
The average, RMS value, and standard deviation of a vector are related by the formula. Equation 3.5
$$rms(x)^2 = avg(x)^2 +std(x)^2 $$This formula is derived on page 63

### Properties of standard deviation.
* *Adding a constant*. For any vector $x$ and any number $a$, we have $$std(\vec x+a \vec 1) =
std(x) $$Adding a constant to every entry of a vector does not change  its standard deviation
* *Multiplying by a scalar*. For any vector $x$ and any number $a$, we have $$std(a\vec x) = |a| std(\vec x)$$Multiplying a vector by a scalar multiplies the standard deviation by the absolute value of the scalar.

### Standardization
For any vector $x$, we refer to $\tilde x  ~  = \vec x - avg(\vec x)\vec 1$ as the *de-meaned* version of $x$, since it has average or mean value zero.

If we then divide by the RMS value of $\tilde x$ (which is the standard deviation of $x$), we obtain the vector
$$
\vec z= {1 \over std(\vec x)} (\vec x-avg(\vec x)\vec 1)
$$

> [!NOTE] Features of Standardized Version
> This vector $\vec z$ is called  the *standardized version of $\vec x$*. It has 
> - Mean or average of zero.
> - Standard deviation one.

> [!NOTE] Adding, subtracting, multiplying and dividing a set or a vector by a number
> - If the transformation involves adding/subtracting, then the mean is shifted by the same amount. The standard deviation is not changed. 
> - If the transformation involves multiplying/dividing, then both the mean and standard deviation are multiplied by this number.

____
## 3.4 Angle

### Cauchy-Schwarz inequality
An important inequality that relates norms and inner products is the Cauchy-Schwarz inequality:
$$
|a^Tb| ≤ ||a||*||b||
$$
where  $a$ and $b$ are $n-vectors$. Formula derived on page 67

### Angle between vectors
The angle between two non-zero vectors $a$ and $b$ 
$$
\theta = \arccos({a^Tb \over ||a||\;||b||})
$$
where $\arccos$ denotes the inverse *cosine*, normalized to lie in the interval $[0, \pi]$. In other words, we dene $\theta$ as the unique number between $0$ and $\pi$ that satisfies:
$$
a^Tb=||a||\;||b||\cos\theta
$$

The angle is a symmetric function of $a$ and $b$: We have $\angle(a,b)$. The angle is not affected by scaling each of the vectors by a **positive** scalar: We have,
for any vectors $a$ and $b$, and any positive numbers $\alpha$ and $\beta$ 
$$
\angle (\alpha a, \beta b)= \angle (a,b)
$$
### Acute and obtuse angles

* If the angle is $\pi/2 = 90°$ i.e., $a^T b = 0$, the vectors are said to be *orthogonal*. We write $a \perp b$  if $a$ and $b$ are orthogonal. (By convention, we also say that a zero vector is orthogonal to any vector.)
* If the angle is zero, which means $a^Tb = ||a||\; ||b||$, the vectors are *aligned*. Each vector is a positive multiple of the other. 
* If the angle is $\pi = 180°$, which means $a^T b = -||a|| \; ||b||$, the vectors are *anti-aligned*. Each vector is a negative multiple of the other.
* If $\angle (a,b) < \pi/2 = 90$, the vectors are said to make an *acute angle*. This is the same as $a^Tb >0$, i.e., the vectors have a positive inner product.
* If $\angle (a,b) > \pi/2 = 90$, the vectors are said to make *obtuse angle*. This is the same as $a^Tb<0$ i.e., the vectors have negative inner product.
![[Figure 3.6 Angles.png]]

### Norm of sum via angles 
Equation 3.6
For vectors $x$ and $y$ 
$$||x+y||^2=||x||^2 + 2x^Ty+ ||y||^2= ||x||^2 +2||x||\;||y||\cos(\theta)+||y||^2$$

* If $x$ and $y$ are aligned $(\theta=0)$, we have $||x+y||=||x|| +||y||$. Thus, their norms add.
* If $x$ and $y$ are orthogonal $(\theta = 90)$ , we have $||x+y||^2 = ||x||^2+||y||^2$ . In this case the norm-squared values add, and we have $||x+y||=\sqrt{||x||^2+||y||^2}$. This formula is sometimes called Pythagorean theorem. 

### Correlation coefficient.
Suppose $a$ and $b$ are $n-vectors$, with associated de-meaned
vectors
$$
\tilde a= \vec a-avg(\vec a)\vec 1,\;\;\;\; \tilde b=\vec b-avg(\vec b)\vec 1
$$
Assuming these de-meaned vectors are not zero (which occurs when the original vectors have all equal entries), we dene their *correlation coefficient* as
$$
\rho={\tilde a^T\tilde b \over ||\tilde a||\; ||\tilde b||}
$$
Thus, $\rho = cos \theta$, where $\theta = \angle(\tilde a, \tilde b)$. 

We can also express the correlation coefficient in terms of the vectors $u$ and $v$ obtained by standardizing $a$ and $b$. With $u = \tilde a  /std(a)$
and $v = \tilde b / std(b)$, we have
$$
\rho={u^Tv \over n}
$$

> [!NOTE] Title
> The correlation coeffcient tells us how the entries in the two vectors vary together. High correlation (say,$\rho = 0,8$) means that entries of $a$ and $b$ are typically above their mean for many of the same entries. The extreme case$\rho = 1$ occurs only if the vectors $\tilde a$ and $\tilde b$ are aligned, which means that each is a positive multiple of the other, and the other extreme case $\rho = -1$ occurs only when $\tilde a$ and $\tilde b$ are negative multiples of each other. See figure 3.8

![[Lecture 1.1 - Figure 3.7 correlation coefficient.png]]

### Standard deviation of sum
Re-read, standard deviation of sum  related to correlation coefficient
### Units for heterogeneous vector entries. 
When the entries of vectors represent different types of quantities, the choice of units used to represent each entry affects the angle, standard deviation, and correlation between a pair of vectors. The discussion on page 51, about how the choice of units can affect distances between pairs of vectors, therefore applies to these quantities as well. The general rule of thumb is to choose units for different entries so the typical vector entries have similar sizes or ranges of values.
