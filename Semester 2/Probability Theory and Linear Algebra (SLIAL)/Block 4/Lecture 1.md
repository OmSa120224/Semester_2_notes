Date: 9/04/2024
Literature: DTG Book 7.1-7.26
___
# An Introduction to Discrete Probability

## 7.1.2 Finite Probability
- An **experiment** is a procedure that yields one of a given set of possible outcomes. 
- The **sample** space of the experiment is the set of possible outcomes. 
- An **event** is a subset of the sample space.


> [!NOTE] Laplace’s definition of the probability of an event with finitely many possible outcomes
> If S is a finite nonempty sample space of equally likely outcomes, and $E$ is an event, that is, a subset of $S$, then the probability of $E$ is $p(E) = {|E| \over |S|}$

## 7.1.3 Probabilities of Complements and Unions of Events


> [!NOTE] THEOREM 1
> Let E be an event in a sample space $S$. The probability of the event $\overline{E} = S − E$, the complementary
event of E, is given by $p(E) = 1 − p(E)$


> [!NOTE] THEOREM 2
> Let $E_1$ and $E_2$ be events in the sample space $S$. Then
$p(E_1 ∪ E_2) = p(E_1) + p(E_2) − p(E_1 ∩ E_2).$

## 7.1.4 Probabilistic Reasoning
The Monty Hall Three-Door Puzzle

____
# Probability Theory



## 7.2.2 Assigning Probabilities


Let $S$ be the sample space of an experiment with a finite or countable number of outcomes. We assign a probability $p(s)$ to each outcome $s$. We require that two conditions be met:
- The first: States that the probability of each outcome is a nonnegative real number no greater than 1.
$$0≤ p(s) ≤ 1 \;\;for\;\; each\;\; s ∈ S$$ 
The second: States that the sum of the probabilities of all possible outcomes should
be 1
$$\sum_{s \in S} p(s)=1$$
The function $p$from the set of all outcomes of the sample space $S$ is called a **probability distribution**.


> [!NOTE] Definition 1
> Suppose that $S$ is a set with $n$ elements. The **uniform distribution** assigns the probability $1\over n$ to each element of $S$.

We now define the probability of an event as the sum of the probabilities of the outcomes in this event.


> [!NOTE] Definition 2
> The probability of the event $E$ is the sum of the probabilities of the outcomes in $E$. That is, $$p(E)= \sum{s \in E} p(s) $$
> (Note that when E is an infinite set, $\sum{_{s∈E}}\; p(s)$ is a convergent infinite series.)



## 7.2.3 Probabilities of Complements and Unions of Events



> [!NOTE] THEOREM 1
> If $E_1, E_2 ,…$ is a sequence of pairwise disjoint events in a sample space $S$, then $$p(\bigcup_{i}E_i = \sum_{i}p(E_i)$$
> (Note that this theorem applies when the sequence $E1, E2,…$consists of a finite number or a countably infinite number of pairwise disjoint events.)


## 7.2.4 Conditional Probability
Ex, i


In general, to find the conditional probability of $E$ given $F$, we use $F$ as the sample space. For an outcome from $E$to occur, this outcome must also belong to $E ∩ F$. With this motivation, we make Definition 3.

> [!NOTE] Definition 3
> Let $E$ and $F$ be events with $p(F) > 0.$ The conditional probability of $E$ given $F$, denoted by $p(E ∣ F)$, is defined as $$p(E|F)={p(E \cap F) \over p(F)}$$



## 7.2.5 Independence
Remember the definition in the slides. 

When two events are independent, the occurrence of one of the  vents gives no information about the probability that the other event occurs.
> [!NOTE] Definition 4
> The events $E$ and $F$ are independent if and only if $p(E ∩ F) = p(E)p(F)$.





**PAIRWISE ANDMUTUAL INDEPENDENCE**: We can also define the independence of more than two events. However, there are two different types of independence, given in Definition 5.


> [!NOTE] Definition 5
> The events $E_1, E_2,…, E_n$ are pairwise independent if and only if $p(E_i ∩ E_j) = p(E_i)p(E_j)$ for all pairs of integers $i$ and $j$ with $1 ≤ i < j ≤ n$. These events are mutually independent if $p(E_{i_1} ∩ E_{i_2} ∩⋯∩ E_{i_m}) = p(E_{i_1})p(E_{i_2})⋯p(E_{i_m})$ whenever
$ij, j = 1, 2,…, m$, are integers with $1 ≤ i_1 < i_2 < ⋯ < i_m ≤ n$ and $m ≥ 2$.



## 7.2.6 Bernoulli Trials and the Binomial Distribution
Each performance of an experiment with two possible outcomes is
called a **Bernoulli trial**. In general, a possible outcome of a Bernoulli trial is called a **success** or a **failure**. If $p$ is the probability of a success and $q$ is the probability of a failure, it follows that $p + q = 1$.



> [!NOTE] THEOREM 2
> The probability of exactly $k$ successes in n independent Bernoulli trials, with probability of success $p$ and probability of failure $q = 1 − p$, is $$C(n, k)p^kq^{n−k}.$$


We denote by $b(k; n, p)$ the probability of $k$ successes in $n$ independent Bernoulli trials with probability of success $p$ and probability of failure $q = 1 − p$. 

Considered as a function of $k$, we call this function the **binomial distribution**. Theorem 2 tells us that $b(k; n, p) = C(n, k)p^kq^{n−k}$.

Note that the sum of the probabilities that there are k successes when n independent Bernoulli trials are carried out, for $k = 0, 1, 2,…, n,$ equals $$\sum_{k=0}^{n}C(n,k)p^kq^{n-k}=(p+q)^n=1 $$



``
