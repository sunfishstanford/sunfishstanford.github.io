---
layout: post
usemathjax: true
categories: [math]
title: "What I learned from Terry Tao's paper on differential forms and integration"
# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

I came across this awesome writeup from Terry Tao explaining [differential forms and integration](https://www.math.ucla.edu/~tao/preprints/forms.pdf).

With the help of this paper, I think I finally understand the basic idea of why differential forms are fundamental to integrals. I think the central idea is:

> A one-dimensional signed definite integral \\( \int_\gamma \omega \\) is a map from a path \\(\gamma\\) to a real number. The same concept is generalized to higher dimensional integrals over surfaces/volumes/etc.

We are used to obsessing about the "\\(f(t)\\)" in the integral \\(\int f(t) dt \\) because of all the drills we did in math class, where we learned a bunch of rules to calculate the integral based on what \\(f(t)\\) is. But if we view the integral from this new perspective, then it's clear how differential forms play a fundamental role. A differential form (at a given point on the manifold) is a map from one or more vectors to a real number. And of course, here the relevant vectors are defined by the integration path/surface/etc. (A path maps to a series of tangent vectors, a surface maps to a series of vector pairs, etc.) So this is how differential forms enable signed definite integrals to map from paths/surfaces/etc. to a real number.

Double-clicking for a bit more detail, focusing on one-dimensional integrals:
- At a given point on a differential manifold, a vector at that point can be considered to be the velocity vector of a parametrized path \\(\gamma(t)\\) going through that point, where \\(t\\) is in an interval on the real line.
- Therefore, a given \\(\gamma\\) induces a set of tangent vectors along its path. 
- A given differential 1-form \\(\omega\\) maps each point along the path to a functional, which in turn maps the tangent vector to a real number. As Tao's paper explains (even as he expresses his disapproval of this notation), for every 1-form there is a unique vector field \\(F:\mathbb{R}^n \rightarrow \mathbb{R}^n\\) such that its dot product with the tangent vector is equivalent to the action of the 1-form on the tangent vector. Note that the integral of the dot product of a vector field with the tangent vector (the velocity vector of the path) is precisely the definition of the [line integral of a vector field](https://en.wikipedia.org/wiki/Line_integral#Line_integral_of_a_vector_field).

- The result is that for a given vector field \\(F\\) that is equivalent to a 1-form \\(\omega\\), you can map each value of \\(t\\) (representing a point along the path \\(\gamma\\)) to a real number, and integrating this over \\(t\\) gives us the line integral of \\(F\\).


