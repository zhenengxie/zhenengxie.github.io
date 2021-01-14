---
title: Lévy--Khintchine Representation
layout: post
tags: [probability theory, levy processes]
---

The Lévy--Khintchine representation theorem provides a characterisation of all infinitely divisible random variables. In particular it gives an explicit form for the characteristic function of all infinitely divisible measure. This post aims to give intuition on what the terms in the moment generating function mean.

There is slightly different form of the Lévy--Khintchine theorem for Lévy processes, but we'll focus on infinitely divisible random variables in this post.

{: .notice}
For simplicity, all random variables in this post are $$\R^d$$-valued unless otherwise stated. 

# Infinite divisibility

A random variable $$X$$ is *infinitely divisible* if for all $$n \geq 1$$ there are independent and identically distributed random variables $$Y_1, \ldots, Y_n$$ such that $$X$$ and $$\sum_{i=1}^n Y_i$$ have the same law.

Two important properties of infinitely divisible random variables are the following:
- The sum of independent infinitely divisible random variables is infinitely divisible.
- The weak limit of independent infinitley divisible random variables if infinitely divisible.

Now let us list three important classes of infinitely divisible random variables.

## Constant random variables

A boring but important class of infinitely divisible random variables. Constant random variables are indepedent of everything so for all $$c \in \R$$ we can write $$c = \sum_{i=1}^n \frac{c}{n}$$ to see that $$c$$ is infinitely divisible.

## Gaussian random variables

There are multiple ways to define a multivariate Gaussian but for our purposes it's easiest to define it via its characteristic function. Let $$\mu \in \R^d$$ and $$\Sigma$$ be a $$d \times d$$ matrix. Then we write $$X \sim N(\mu, \Sigma)$$ if 

$$ \E[e^{iX}] = \exp(i \mu \cdot u + \tfrac{1}{2} u \cdot \Sigma u). $$

We can show such random variables exist for all $$\mu$$ and all positive semi-definite $$\Sigma$$.

### Sums of independent Gaussians

Let $$X_1 \sim N(\mu_1, \Sigma_1)$$ and $$X_2 \sim N(\mu_2, \Sigma_2)$$ where the $$X_1$$ and $$X_2$$ are independent. Then by the independence property

$$
\begin{align*}
\E[e^{i(X_1 + X_2)}]
&= \E[e^{i X_1}] \E[e^{i X_2}] \\
&= \exp(i \mu_1 \cdot u + \tfrac{1}{2} u \cdot \Sigma_1 u) \exp(i \mu_2 \cdot u + \tfrac{1}{2} u \cdot \Sigma_2 u) \\
&= \exp(i (\mu_1 + \mu_2) \cdot u + \tfrac{1}{2} u \cdot (\Sigma_1 + \Sigma_2) u).
\end{align*}
$$

Hence we see that $$X + Y \sim N(\mu_1 + \mu_2, \Sigma_1 + \Sigma_2)$$.

### Infinite divisibility of Gaussians


## Compound Poisson random variables

Let $$\lambda \geq 0$$ and $$\mu$$ be a probability measure on $$\R^d$$. Suppose $$N \sim \text{Poisson}(\lambda)$$ and let $$Z_1, Z_2, \ldots$$ be i.i.d. with law $$\mu$$ independently of $$N$$. Then

$$X = \sum_{i=1}^N Z_i$$

is a compound Poisson random variable.

Rather than working with two parameters, we can combine $$\lambda$$ and $$\mu$$ into a single measure $$\nu = \lambda \mu$$. From $$\nu$$ we can recover $$\lambda$$ since $$\lambda = \nu(\R^d)$$. We then write $$\pi(\nu)$$ for the distribution of $$X$$.

### Characteristic function of compound Poisson processes

If $$X \sim \pi(\nu)$$ we can compute that

$$ \E[e^{i u \cdot X}] = \exp\left\{ \int_{\R^d} (e^{iu \cdot x} - 1) \mu(\dif x) \right\}. $$

### Sums of indepedent compound Poissons

Suppose $$X_1 \sim \pi(\nu_1))$$ and $$X_2 \sim \pi(\nu_2)$$ where $$\nu_1$$ and $$\nu_2$$ are finite measures on $$\R^d$$. Suppose further that $$X_1$$ and $$X_2$$ are independent. Then checking the characteristic function of $$X_1 + X_2$$ shows that $$X_1 + X_2 \sim \pi(\nu)$$ where

$$ \nu(A) = \nu_1(A) + \nu_2(A). $$



# Lévy--Khintchine

Now we finally state the main theorem.

<div class=theorem>
#### Theorem: (Lévy--Khintchine)

For a Lévy triple $$(b, A, \nu)$$ let $$\phi_{b, A, \nu}(u) = \exp\left\{ \eta_{b, a, \nu}(u) \right\}$$ where

$$
\eta_{b, A, \nu}(u) =
i b \cdot u +
\frac{1}{2} u \cdot A u +
\int_{\abs{x} \geq 1} \left( e^{i x \cdot u}  - 1\right) \mathop{}\!\nu(\dif x) +
\int_{\abs{x} < 1} \left( e^{i x \cdot u}  - 1 - i x \cdot u \right) \mathop{}\!\nu(\dif x).
$$

If $$X$$ is infinitely divisible random variable then the characterstic function of $$X$$ is $$\phi_{b, A, \nu}$$ for some Lévy triple $$(b, A, \nu)$$.

Conversely for all Lévy triples, $$\phi_{b, A, \nu}$$ is the characteristic function of some infinitely divisible random variable.
</div>

## Analysis of terms

The $$b \cdot u$$ and $$\tfrac{1}{2} u \cdot A u$$ terms are straightforwards to intepret, they correspond to the sum of a constant random variable with value $$b$$ and a $$N(0, A)$$ random variable.

The last term is harder to understand. It almost looks like a compound Poisson random variable but with two differences. Firstly $$\nu$$ is not finite. Secondly there is a compensating term.

First we examine the case where . Then in fact the compensating term is unecessary, we could rearrange $$\eta$$ as 

thus we see the compensating term has been absorbed into $$()$$. $$\nu$$ is finite on any set not containing a neighbourhood of 0, thus $$\nu$$ is finite on for all $$n$$. Therefore by writing

we see that the last term corresponds to an infinite sum of compound Poisson random variables.

## Compound Poissons are enough