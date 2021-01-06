---
title: "Strong, weak and weak star topologies"
layout: post
share: true
---

Norms on finite dimensional spaces have a very nice feature: the unit ball is compact. In fact for the unit ball to be compact in a normed vector space, it is not only sufficient but necessary for the space to be finite dimensional. As soon as we are working with infinite dimensional spaces, we lose compactness. This is one of the motivations for the weak and weak star topologies.

The more coarse a space is, the more "likely" it is to be compact. After all there are fewer open covers to find finite subcovers for. This tells us what we need to do in order to make the unit ball compact again, we need to throw away open sets.

Why don't we just throw away all the open sets? Then we'd have a very boring topology: the coarse topology. In particular under the topology the only functions that are continuous are the constant functions. We need enough open sets remaining so that certain functions which were continuous under the normed topology are still continuous.

# Initial topologies

Initial topologies are motivated by the following question. Given a set of functions $$f_i: X \to Y$$ for $$i \in I$$ some indexing set and $$Y$$ a space with a specified topology, what topology is needed on $X$ to make all the functions $$f_i$$ continuous? The smallest such topology is called the initial topology.

You're probably already met initial topologies, even if you haven't been told they are such. The subspace topology is just the initial topology with respect to the inclusion function and the product topology is just the initial opology with respect to the projection functions.

So now the question is which functions do we still want to be continuous?

# The weak topology

Seen as we are in a vector space, a natural choice of functions are the linear functions $$V \to \mathbb R$$ which were already continuous with respect to the normed topologies.