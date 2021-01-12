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

### Relation to compound Poisson processes

An intuitive way to think about these processes is the following:

{: .notice--info}
Jumps of size $$x$$ occur with infinitesimal rate $$\nu(\dif x)$$.

### Sums of independent compound Poissons

### Infinite divisibility of compound Poissons

# Lévy--Khintchine

Now we finally state the main theorem.

<div class=theorem>
#### Theorem: (Lévy--Khintchine)

For a Lévy triple $$(b, A, \nu)$$ let $$\phi_{b, A, \nu}(u) = \exp\left\{ \eta_{b, a, \nu}(u) \right\}$$ where

$$
\eta_{b, A, \nu}(u) =
b \cdot u +
\frac{1}{2} u \cdot A u +
\int_{\abs{x} \geq 1} \left( e^{i x \cdot u}  - 1\right) \mathop{}\!\nu(\dif x) +
\int_{\abs{x} < 1} \left( e^{i x \cdot u}  - 1 - x \cdot u \right) \mathop{}\!\nu(\dif x).
$$

If $$X$$ is infinitely divisible random variable then the characterstic function of $$X$$ is $$\phi_{b, A, \nu}$$ for some Lévy triple $$(b, A, \nu)$$.

Conversely for all Lévy triples, $$\phi_{b, A, \nu}$$ is the characteristic function of some infinitely divisible random variable.
</div>