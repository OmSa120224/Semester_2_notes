Date: 15/04/2023
Literature: DTG Book Sections 7.2.7, 7.4
_____


## 7.2.7 Random Variables
> [!NOTE] Definition
> A *random variable* is a function from the sample space of an experiment to the set of real numbers. That is, a random variable assigns a real number to each possible outcome.

**Remark**: Note that a random variable is a function. It is not a variable, and it is not random! 


> [!NOTE] Title
> The distribution of a random variable $X$ on a sample space $S$ is the set of pairs $(r, p(X = r))$ for all $r ∈ X(S)$, where $p(X = r)$ is the probability that $X$ takes the value $r$. (The set of pairs in this distribution is determined by the probabilities $p(X = r)$ for $r ∈ X(S)$.)

___
# 7.4 Expected Value and Variance

The **expected value** in discrete math represents the average outcome you'd expect if you repeated an experiment many times.


## 7.4.2 Expected Values


> [!NOTE] Definition
> The expected value, also called the *expectation* or *mean*, of the random variable $X$ on the sample space $S$ is equal to $$E(X)=\sum_{p \in S}p(s)X(s)$$
The *deviation* of *X* at *s ∈ S* is *X(s) − E(X)*, the difference between the value of *X* and the mean of *X*.



> [!NOTE] THEOREM 1
> If $X$ is a random variable and $p(X = r)$ is the probability that $X = r$, so that 
> $$p(X = r) = \sum_{s∈S,X(s)=r} p(s)$$
> , then 
> $$E(X)=\sum_{r \in X(S)}P(X=r)r  $$
> In words the expected value of $X$ is the sum of the probabilities of $X$ taking the value $r$ multiplied by $r$. 




> [!NOTE] THEOREM 2
> The expected number of successes when $n$ mutually independent Bernoulli trials are performed, where $p$ is the probability of success on each trial, is $np$.



## 7.4.3 Linearity of Expectations


> [!NOTE] THEOREM 3
> If $X_i, i = 1, 2,…, n$ with $n$ a positive integer, are random variables on $S$, and if $a$ and $b$ are real numbers, then
(i) $E(X_1 + X_2 +⋯+ X_n) = E(X_1) + E(X_2) +⋯+ E(X_n)$
(ii) $E(aX + b) = aE(X) + b$.


## 7.4.4 Average-Case Computational Complexity


## 7.4.5 The Geometric Distribution

![[7.4.5 example 10.png]]
> [!NOTE] Definition
> A random variable $X$ has a *geometric distribution* with parameter *p* if $p(X = k) =
(1 − p)k−1p$ for $k = 1, 2, 3,…,$ where $p$ is a real number with $0 ≤ p ≤ 1$.

When we computed the expected value of the number of flips required before a coin comes up tails, we proved Theorem 4.


> [!NOTE] THEOREM 4
> If the random variable $X$ has the geometric distribution with parameter $p$, then $E(X) = 1∕p$.

## 7.4.6 Independent Random Variables

> [!NOTE] Title
>The random variables $X$ and $Y$ on a sample space $S$ are independent if
$p(X = r1$ and $Y = r2) = p(X = r1) ⋅ p(Y = r2)$
or in words, if the probability that $X = r_1$ and $Y = r_2$ equals the product of the probabilities
that $X = r_1$ and $Y = r_2$, for all real numbers $r_1$ and $r_2$.



> [!NOTE] THEOREM 5
> If $X$ and $Y$ are independent random variables on a sample space $S$, then $E(XY) = E(X)E(Y)$.


## 7.4.7 Variance


> [!NOTE] Definition 
> Let $X$ be a random variable on a sample space $S$. The variance of $X$, denoted by $V(X)$, is $$V(X) =\sum_{s∈S}(X(s) − E(X))^2p(s).$$
That is, $V(X)$ is the weighted average of the square of the deviation of $X$. The standard deviation of $X$, denoted $𝜎(X)$, is defined to be $\sqrt{V(X)}.$


Theorem 6 provides a useful simple expression for the variance of a random variable.


> [!NOTE] THEOREM 6
> If $X$ is a random variable on a sample space $S$, then $V(X) = E(X^2) − E(X)^2$.

We can use Theorems 3 and 6 to derive an alternative formula for $V(X)$ that provides some insight into the meaning of the variance of a random variable


> [!NOTE] COROLLARY 1
> If $X$ is a random variable on a sample space $S$ and $E(X) = 𝜇$, then $V(X) = E((X − 𝜇)^2)$.

Corollary 1 tells us that the variance of a random variable $X$ is the expected value of the square of the difference between $X$ and its own expected value.

Another useful property is that the variance of the sum of two or more independent random variables is the sum of their variances. The formula that expresses this property is known as **Bienaymé’s formula**.


> [!NOTE] THEOREM 7
> **Bienaymé’s formula** If $X$ and $Y$ are two independent random variables on a sample space $S$, then $V(X + Y) = V(X) + V(Y)$. Furthermore, if $X_i, i = 1, 2,…, n$, with $n$ a positive integer, are pairwise independent random variables on $S$, then $V(X_1 + X_2 +⋯+ X_n) = V(X_1) + V(X_2) +⋯+ V(X_n)$.


## 7.4.8 Chebyshev’s Inequality
How likely is it that a random variable takes a value far from its expected value? Theorem 8, called Chebyshev’s inequality, helps answer this question by providing an upper bound on the probability that the value of a random variable differs from the expected value of the random variable by more than a specified amount.


> [!NOTE] THEOREM 8
> **CHEBYSHEV’S INEQUALITY** Let $X$ be a random variable on a sample space $S$ with probability function $p$. If r is a positive real number, then $$p(|X(s) − E(X)| ≥ r) ≤ {V(X) \over r^2}.$$

