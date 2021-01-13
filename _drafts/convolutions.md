---
title: Convolution of probability measures
layout: post
tags: [levy processes, probability theory]
---

You may be familiar with the convolution of functions $$\R^d \to \R$$. The convolution of probability measures is defined similarly

Let $$\mu_1$$ and $$\mu_2$$ be probability measures on $$\R^d$$. Then their *convolution* $$\mu_1 * \mu_2$$ is defined by

$$ (\mu_1 * \mu_2)(A) = \int_{\R^d} \mu_1(A + x) \mu_2(\dif x) $$

for all Borel sets $$A \subset \R^d$$.

<div class="theorem">
#### Theorem: (Addition of indepedent random variables and convolution)

Suppose that $$X_1$$ has law $$\mu_1$$ and $$X_2$$ has law $$\mu_2$$. Suppose further that $$X_1$$ and $$X_2$$ are indepedent. Then $$X_1 + X_2$$ has law $$\mu_1 * \mu_2$$.
</div>

By using the above we can prove the following algebraic properties for convolution.

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

{: .notice--success}
The set of probability measures on $$\R^d$$ is a commutative semigroup under convolution.

In particular we don't need brackets when writing convolutions and can switch the order of convolution as we desire.