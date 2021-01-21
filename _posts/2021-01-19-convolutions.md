---
title: Convolution of probability measures
layout: post
tags: [levy processes, probability theory]
---

This is going to be the first of a series of posts accompanying the Lévy processes reading groups. Core to the study of Lévy processes are infinitely divisible random variables, but before we define those we first need to understand what a convolution of probability measures is.

Let's start with the definition. Let $$\mu_1$$ and $$\mu_2$$ be probability measures on $$\R^d$$. Then their *convolution* $$\mu_1 * \mu_2$$ is defined by

$$ (\mu_1 * \mu_2)(A) = \int_{\R^d} \mu_1(A + y) \mu_2(\dif y) $$

for all Borel sets $$A \subset \R^d$$.

# Summing indepedent variables gives convolutions

The above definition isn't a very intuitive way of thinking about convolutions. The following theorem gives solid motivation as to why we define the convolution the way that we do.

<div class="theorem">
#### Theorem: (Addition of indepedent random variables and convolution)

Suppose that $$X_1$$ has law $$\mu_1$$ and $$X_2$$ has law $$\mu_2$$. Suppose further that $$X_1$$ and $$X_2$$ are indepedent. Then $$X_1 + X_2$$ has law $$\mu_1 * \mu_2$$.
</div>

<div class="proof">
*Proof*: Let $$A \subset \R^d$$ be a Borel subset. Then

$$
\begin{align*}
\prob(X_1 + X_2 \in A)
&= \int_{\R^d} \int_{\R^d} \indi_A(x + y) \mu_1(\dif x) \mu_2(\dif y) \\
&= \int_{\R^d} \int_{\R^d} \indi_{A + y}(x) \mu_1(\dif x) \mu_2(\dif y) \\
&= \int_{\R^d} \mu_1(A + y) \mu_2(\dif y)
= (\mu_1 * \mu_2)(A).
\end{align*}
$$

Thus $$X_1 + X_2$$ has law $$\mu_1 * \mu_2$$ as required.
</div>

# Algebraic properties of convolutions

The previous theorem gives a quick way to prove the following basic properties of convolutions.

<div class="theorem">
#### Corollary: 

Let $$\calM_1(\R^d)$$ denote the set of all probability measures on $$\R^d$$. Then the following properties hold.

- **Closure**: For all $$\mu_1$$ and $$\mu_2$$ in $$\calM_1(\R^d)$$,
\\[ \mu_1 * \mu_2 \in \calM_1(\R^d). \\]
- **Identity**: For all $$\mu \in \calM_1(\R^d)$$,
\\[ \delta_0 * \mu = \mu * \delta_0 = \mu. \\]
- **Associativity**: For all $$\mu_1$$, $$\mu_2$$ and $$\mu_3$$ in $$\calM_1(\R^d)$$,
\\[ (\mu_1 * \mu_2) * \mu_3 = \mu_1 * (\mu_2 * \mu_3). \\]
- **Commutativity**: For all $$\mu_1$$ and $$\mu_2$$ in $$\calM_1(\R^d)$$,
\\[ \mu_1 * \mu_2 = \mu_2 * \mu_1. \\]
</div>

<div class="proof">
*Proof*: Fix $$\mu_1$$, $$\mu_2$$ and $$\mu_1 \in \calM_1(\R^d)$$. Then there is a probability space on which we can define indepedent random variables $$X_1$$, $$X_2$$ and $$X_3$$ where $$X_i$$ has law $$\mu_i$$ for $$i = 1, 2, 3$$.

Closure follows because $$\mu_1 * \mu_2$$ is the law of $$X_1 + X_2$$ and thus is a probability measure on $$\R^d$$.

$$\delta_0$$ is the identity since $$\delta_0$$ is the law of a constand random variable with value 0.

Associativity is inherited from addition, noting that $$X_1 + X_2$$ is indepedent of $$X_3$$ and $$X_1$$ is indepedent of $$X_2 + X_3$$.

Finally commutativity is also inherited from addition.
</div>

The previous corollary can in fact be summarised as follows:

{: .notice--info}
The set of probability measures on $$\R^d$$ is a commutative semigroup under convolution.

So we don't need to worry about brackets or the other of convolutions. However unlike addition there are, in general, no inverses.

{: .notice--danger}
$$\mu$$ has no convolutional inverse unless $$\mu = \delta_x$$ for some $$x \in \R^d$$.

In the language of random variables, the only thing we can add on to $$X$$ to cancel it out is $$-X$$. However as long as $$X$$ is not almost surely constant, $$X$$ and $$-X$$ are not indepedent.

# Convolutional powers and roots

Since convolution is associative, we can unambigiously define the $$n$$th convolutional power of a measure $$\mu$$ as

$$\mu^{*n} \defeq \underbrace{\mu * \cdots * \mu}_{\text{$n$ times}}.$$

Correspondingly we say a probability measure $$\nu$$ is the convolutional $$n$$th root of $$\mu$$ if $$\mu = \nu^{*n}$$.

{: .notice--danger}
Convolutional $$n$$th roots are, in general, neither guaranteed to exist nor unique.

For example a Bernoulli random variable has no second convolution root. We will finish this post by stating a few equivalent conditions for $$\nu$$ to be the $$n$$th convolutional root of $$\mu$$.

<div class="theorem">
#### Theorem:

Let $$\mu$$ and $$\nu$$ be a probability measures on $$\R^d$$. Then the following are equivalent.

1. $$\nu$$ is an $$n$$th convolution root of $$\mu$$.
2. There exists i.i.d. random variables $$Y_1, \ldots, Y_n$$ with law $$\nu$$ such that $$\sum_{i=1}^n Y_i$$ has law $$\mu$$.
3. The Fourier transform of $$\nu$$ is an $$n$$th root of the Fourier transform of $$\mu$$.
</div>

The equivalence of 1 and 2 follows from the first theorem. The equivalence of 2 and 3 follows from the fact that is two random variables are independent, the Fourier transform of their sum is the product of Fourier transforms of the individual random variables.

The characterisation in terms of Fourier transforms is especially important. This is as the $$n$$root of a complex number is something we understand quite well, unlike the more abstract definition of a convoultional root. This will come into play when we talk about infinitely divisible random variables.