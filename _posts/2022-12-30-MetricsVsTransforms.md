---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math, physics]
title: "How to think about metrics versus coordinate transformations"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

When you first learn about vectors and dot products in Cartesian space, it's all pretty simple. And then you learn about similar concepts in something like Minkowski space or even complicated things like curved spacetime, you see things like:

$$
ds^2 = g_{\mu \nu} \mathrm{dx}^\mu \mathrm{dy}^\nu 
$$

and

$$
x^{\mu'} = {\Lambda^{\mu'}}_\nu x^\nu .
$$

So it becomes easy to get confused between the metric $$g_{\mu \nu}$$ versus the coordinate transformation $${\Lambda^{\mu'}}_\nu$$. And what's even more confusing is that both the metric and the coordinate transformation have inverse transforms that take them to the delta function (the identity tranform).

So I've gathered some of the key facts to help myself (and I hope, to help others also) keep those two things straight.

Metric
------

One of the main functions of a metric $$g_{\mu \nu}$$ is to compute inner products in a vector space. This lets us define a quantity such as the spacetime interval *within a given coordinate system*. And the upper and  Because we usually deal with real-valued inner products in relativity (e.g., we define the spacetime interval in a symmetric way) and differential geometry, that means the inner product is symmetric, which means the metric is symmetric:

$$
g_{\alpha \rho} = g_{\rho \alpha} .
$$

Because we often want to manipulate expresssions that include objects that live in the dual space (e.g., 1-forms), we use raised and lowered indices to keep track. And so we *define* the inverse metric $$g^{\mu \nu}$$ to let us convert from the vector space to the dual space and back to the vector space. For example:

$$
V^\mu = g^{\mu \nu} V_\nu .
$$

And since the mapping from the vector space to the dual space is isomorphic, the roundtrip map must be the identity, which means that the metric and inverse metric are inverses of each other:

$$
g_{\mu \nu} g^{\mu \rho} = g_{\mu \nu} g^{\rho \mu} = g_{\nu \mu} g^{\rho \mu} = \delta^\rho_\nu
$$

Coordinate transformation
---------------
A coordinate transformation is used when we want to refer to points in a manifold (e.g., a maniform that is a Minkowski space) from the perspectives of two different coordinate systems (using two different charts to map from the local subset of the manifold to $$\mathbb{R}^n$$). So the coordinate transformation is used to go back and forth between the two coordinate systems (reference frames). For example, if the two frames are primed and unprimed inertial frames, and the coordinate transformation is a Lorentz transformation:

$$
x^{\mu'} = {\Lambda^{\mu'}}_\nu x^\nu .
$$

We see that the $$\Lambda$$ has a raised index $$\mu$$ that is primed, and a lowered index $$\nu$$ that is unprimed. This signifies that is transforming from the unprimed frame to the primed frame. So then to go in the reverse direction, you need to apply an inverse transform (e.g., for a Lorentz boost, you use the negative velocity to reverse it), and the inverse transform would be $${\Lambda^{\rho}}_{\mu’}$$. So, similar to above, the roundtrip from unprimed to primed and back gives the identity:

$$
{\Lambda_{\mu’}}^{\rho} {\Lambda^{\mu'}}_\nu = \delta^\rho_\nu .
$$


Useful Links
------------

1. Sean Carroll's [lecture notes on General Relativity, Chapter 1](https://preposterousuniverse.com/wp-content/uploads/grnotes-one.pdf){:target="_blank"} (he also wrote a book on this that is widely used). Eq. (1.29) on pdf page 17 shows the definition of the inverse Lorentz transformation.

2. Sean Carroll's [lecture notes on General Relativity, Chapter 2](https://preposterousuniverse.com/wp-content/uploads/grnotes-two.pdf){:target="_blank"} . Eq. (2.28) on pdf page 17 shows the definition of the inverse metric.
