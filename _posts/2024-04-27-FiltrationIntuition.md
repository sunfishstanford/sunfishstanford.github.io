---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math]
title: "Intuition for filtrations in stochastic processes"
permalink: /:year/:title:output_ext

---
Understanding stochastic processes is important for many fields (e.g., statistical physics, mathematical finance, generative AI), and a *filtration* is a foundational concept. Here is the [Wikipedia definition](https://en.wikipedia.org/wiki/Filtration_(probability_theory)){:target='_blank'}:

> Filtrations are totally ordered collections of subsets that are used to model the information that is available at a given point

This can be a pretty confusing concept (it certainly was for me), so I'd like to share a concrete example to help with the intuition.

Think of a group of kids in a preschool (sorry, these are US-centric examples), where you observe them from afar, not getting to know the individual kids, but just looking at some overall metrics and statistics on their activities and accomplishments.

After some time, the kids will move to different elementary schools. Then they move to different high schools, perhaps colleges, etc. Then they get different jobs, maybe some will get a dog, etc. The point is that over time, they begin to have memberships in different overlapping classes (classes such as which elementary school, which job, whether pet ownership, ...). 

So in the end, each kid will have a unique trajectory through time: a sequence of memberships in these overlapping classes. If we randomly pick a kid and ask what will happen, then each kid in that preschool corresponds to an outcome in the set of all possible outcomes $$\Omega$$ (or equivalently, the entire preschool corresponds to $$\Omega$$). At time $$t=0$$, there is a $$\sigma$$-algebra (also called a *field* in probability theory) $$\mathcal F_0$$ that is a collection of two subsets of $$\Omega$$, namely $$\Omega$$ itself (i.e., the set of all kids in the preschool) and the empty set $$\emptyset$$ (recall that a $$\sigma$$-algebra must be closed under countable unions and complements). 

Suppose that at time $$t_1$$, the kids sort into different elementary schools. Then, there is a $$\sigma$$-algebra $$\mathcal{F}_1$$ that is a collection of all the subsets of kids that went to the same elementary schools plus all countable unions and complements. And therefore $$\mathcal{F}_0 \subseteq \mathcal{F}_1$$.

Next, suppose that after all the kids have finished their education, at time $$t_2$$ they sort into different jobs. Then, there is a $$\sigma$$-algebra $$\mathcal{F}_2$$ that is a collection of all the subsets of kids that have the same job type plus all the subsets in $$\mathcal{F}_1$$ plus countable unions and complements. And therefore $$\mathcal{F}_0 \subseteq \mathcal{F}_1 \subseteq \mathcal{F}_2$$.

Proceeding this way, by considering all times when the kids do or do not become members of various classes, we can construct a filtration $$\mathbb{F}$$ that is the family $$\{\mathcal{F}_t\}$$ of increasing $$\sigma$$-algebras.

At any time $$t$$, the $$\sigma$$-algebra $$\mathcal{F}_t$$ will contain all the subsets of $$\Omega$$ that are measurable at that time $$t$$. If an event (some subset of $$\Omega$$) is not contained in $$\mathcal{F}_t$$, then that event is not measurable, which means that as of time $$t$$ neither that event nor the complement of that event will have occurred.

To make this concrete, assume that the preschool has 6 kids, numbered from 1 to 6. Suppose that at $$t_1$$, #1, #2, and #3 went to elementary school A, and the others went to elementary school B. Then at $$t_2$$, #1 and #2 became teachers and the others went into different careers. Then at $$t_2$$ the event $$\{1,2\}$$ is measurable because it is contained in $$\mathcal{F}_2$$. However, at $$t_2$$ the event $$\{1\}$$ is *NOT* measurable. This is because until $$t_2$$, #1 and #2 have taken the same trajectory. And therefore if we observe a kid who has gone to elementary school A and taken a job as a teacher, we would not be able to decide whether that kid is #1 or #2.


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111993699873026393){:target="_blank"}



[//]: #  https://gist.github.com/pierrejoubert73/902cc94d79424356a8d20be2b382e1ab
