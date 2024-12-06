---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math]
title: "Confusion regarding a math proof using infinums"
permalink: /:year/:title:output_ext

---


There is The proof uses a clever technique where an infinitesimal $$\epsilon$$ is added to one side of an inequality to flip the direction of the inequality.
In Proposition 1.3.2, Donald Cohn's *Measure Theory, 2nd Edition*, a Lebesgue outer measure $$\lambda^*$$ is shown to be an outer measure.  I was confused about why this couldn't be used in the opposite direction. I'd like to share the detailed explanation of why that would not work (which is good, because that means the proof makes sense).

The background
--------

We first repeat here the relevant portions from Cohn's book. We start with the definition of the Lebesgue outer measure:

$$
\lambda^*(A)=\mathrm{inf} \left\{ \sum\limits_i(b_i-a_i):\{(a_i,b_i)\} \in\mathscr{C}_A \right\} 
$$

[define A, C_A]

We also let $$\{A_n\}_{n=1}^{\infty}$$ be an arbitrary sequence of subsets of $$\mathbb{R}$$, and let $$\epsilon$$ be an arbitrary positive number.

For each $$n$$, choose a sequence $$\{ (a_{n,i},b_{n,i})\}_{i=1}^\infty$$ that covers $$A_n$$ and satisfies

$$
\sum\limits_{i=1}^\infty (b_{n,i}-a_{n,i}) < \lambda^*(A_n) + \epsilon/2^n
$$

By "a sequence covers $$A_n$$", we mean that every point inside $$A_n$$ 


In the [prior post on free energy](http://localhost:4000/2023/FreeEnergy2.html){:target="_blank"}, we discussed the role of the Reservoir as the "central banker" of the "energy economy" for a thermodynamic system. In other words, the Reservoir plays a *regulatory* role in the system. I've found this *control theory* perspective on a thermodynamic system to be really helpful for my intuition.


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111361149185984597){:target="_blank"}
