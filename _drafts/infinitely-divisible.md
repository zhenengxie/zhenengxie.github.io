---
title: Infinitely divisible random variables
layout: post
tags: [levy processes, probability theory]
---

Infinitely divisble random variables are key in beginning to understand Lévy processes. The definition is rather simple. A probability measure $$\mu$$ on $$\R^n$$ is infinitely divisible if it has an $$n$$th convolution root for all $$n \geq 1$$.

The rest of this post aims to cover some properties of infinitely divisble random variables, as well as give three important examples of infinitely divisible random variables.

# Uniqueness of $$n$$th root

By definition, the existence of an $$n$$th root of an infinitely divisible random variable is not a problem. Recall in general that $$n$$th convolution roots are not unique. However, it turns out that for infinitely divisible processes we recover uniqueness of the root.

The basic idea is quite simple, we claim that .

In order to make this work, we need a lemma from complex analysis. 

The machinery used here to prove the lemma is a bit overkill, but the basic intuition of the proof is simple. The logarithm is already well defined up to addition of a factor of , but by adding such a factor on we would break continuity. Thus once we fix that , the rest of the logarithm function is uniquely determined by continuity. Existence is a more tricky subject, and basically involves stitching together a bunch of open sets on which the logarithm can be defined by simple composition with a branch of the logarithm

{: .notice--success}
The convolution $$n$$-th root of an infinitely divisible random variable is unique.

# Closure properties of infinitely divisible random variables

# Examples of infinitely divisible distributions

## Constants

## Gaussians

## Compound Poissons