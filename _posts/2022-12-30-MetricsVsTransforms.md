---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math, physics]
title: "Making sense of the metric versus the coordinate transformation"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

When you first learn about vectors and dot products in Cartesian space, they're simple and easy to understand. And then you learn about Minkowski space and curved spacetime, and you see things like:

$$
ds^2 = g_{\mu \nu} \mathrm{dx}^\mu \mathrm{dx}^\nu 
$$

and

$$
x^{\mu'} = {\Lambda^{\mu'}}_\nu x^\nu .
$$

So it becomes easy to get confused about the metric $$g_{\mu \nu}$$ versus the coordinate transformation $${\Lambda^{\mu'}}_\nu$$. And what's even more confusing is that both the metric and the coordinate transformation have similar looking inverse transforms that take them to the delta function (the identity tranform).

So I've gathered some of the key facts to help myself (and to help others also, I hope) keep those two things straight.

Metric
------

One of the main uses of a metric $$g_{\mu \nu}$$ is to compute inner products in a vector space. This lets us define quantities such as the spacetime interval *within a given coordinate system*. In the context of relativity, where we deal with real-valued inner products that are defined to be symmetric, the metric is symmetric:

$$
g_{\alpha \rho} = g_{\rho \alpha} .
$$

Because we want to manipulate both vectors in the vector space and objects that live in the dual space (e.g., 1-forms), we use raised and lowered indices to simplify bookkeeping. And so we *define* the inverse metric $$g^{\mu \nu}$$ to let us convert from the vector space to the dual space and vice versa. For example:

$$
V^\mu = g^{\mu \nu} V_\nu .
$$

And since the mapping from the vector space to the dual space is isomorphic, the roundtrip map must be the identity, which means that the metric and inverse metric are inverses of each other:

$$
g_{\mu \nu} g^{\mu \rho} = g_{\mu \nu} g^{\rho \mu} = g_{\nu \mu} g^{\rho \mu} = \delta^\rho_\nu .
$$

Coordinate transformation
---------------
A coordinate transformation is used when we want to refer to points in a manifold (e.g., spacetime events in Minkowski space) from the perspectives of two different coordinate systems (using two different charts to map from local subsets of the manifold to $$\mathbb{R}^n$$). When we talk about something transforming as a 4-vector or as an invariant tensor, we are thinking of a coordinate transformation. So the coordinate transformation is used to go back and forth between two coordinate systems (reference frames). For example, if the two frames are primed and unprimed inertial frames, and the coordinate transformation is a Lorentz transformation, we have:

$$
x^{\mu'} = {\Lambda^{\mu'}}_\nu x^\nu .
$$

We see that $$\Lambda$$ has a raised index $$\mu$$ that is primed, and a lowered index $$\nu$$ that is unprimed. This signifies a transformation from the unprimed frame to the primed frame. To go in the opposite direction, you need to apply an inverse transform, $${\Lambda^{\rho}}_{\mu’}$$, with a raised unprimed index and a lowered primed index (the inverse Jacobian). So, similar to above, the roundtrip from unprimed frame to primed frame and back gives the identity:

$$
{\Lambda^{\rho}}_{\mu’} {\Lambda^{\mu'}}_\nu = \delta^\rho_\nu .
$$

Key takeaways
-------------
To summarize:
- The metric $$g_{\mu \nu}$$ is involved in inner products and converting between vectors and 1-forms (and their tensor generalizations), always within the same coordinate system.
- The coordinate transformation {\Lambda^{\mu'}}_\nu is involved in transforming between different reference frames or coordinate systems.

Useful Links
------------

1. Sean Carroll's [lecture notes on General Relativity, Chapter 2](https://preposterousuniverse.com/wp-content/uploads/grnotes-two.pdf){:target="_blank"} . Eq. (2.28) on pdf page 17 shows the definition of the inverse metric.

