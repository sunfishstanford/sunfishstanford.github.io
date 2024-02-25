---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math]
title: "Dual of a dual space"
permalink: /:year/:title:output_ext



# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab

---

This is a quick post on dualing spaces. 😎 More specifically, this is a post on the intuition behind the dual of a dual.

>Definition: a vector space $$V$$ has a [dual space](https://en.wikipedia.org/wiki/Dual_space){:target='_blank'} $$V\!\!^*$$, which is a space of the linear [functionals](https://en.wikipedia.org/wiki/Functional_(mathematics)){:target='_blank'} defined on $$V$$.

Functions versus vectors
----------------
I first learned about functionals in the context of the calculus of variations, used in classical mechanics with the principle of stationary action. There, the functional is a map from a trajectory in spacetime to a real number called the *action*. So the trajectory is a vector-valued function of time (think of the spatial coordinates as functions of time, where for a given time we get a spatial vector). 

So we generalize from vector-valued functions to just vectors, and a functional maps a vector to a real number (or to a field element). Think of a column vector, for example, as a map from an index (the index $$i$$ into the column vector) to a real number (the $$i$$-th element of the vector). So as $$i$$ takes on its possible values, the vector maps that into real numbers, just like a function. By taking the discrete index steps to a continuous limit, so that we have an infinite dimensional vector, we see that the vector approximates a continous function. This is, for example, how we can think of a quantum mechanical wavefunction as an infinite dimensional vector (with complex values instead of real values). Just chop up the spatial dimensions into discrete points, assign a complex number to each point, collect that together into a vector, and we get a discrete approximation to the wavefunction.

The dual of a vector
--------------
A linear functional of a vector, where the vector is from $$V$$, is a linear map from that vector to a real number. Since it is linear, its action is fully defined if we know what it does to the basis vectors of $$V$$. If we consider an arbitrary functional $$y^*$$, and we want to find the action of $$y^*$$ on a vector $$x$$ from $$V$$, we simply express $$x$$ as a linear combination of the basis vectors of $$V$$, evaluate $$y^*$$ on each of those basis vectors, and take the linear combination of that. (This is an application of the homomorphism property of the linear map.)

If the basis vectors of $$V$$ are denoted as $$u_i$$, then we can define linear functionals $$u^*_i$$, where the action of these functionals $$u^*$$ on the basis vectors $$u$$ is defined as

$$
u^*_i(u_j) = \delta_{ij}.
$$

So we can define any linear functional $$y^*$$ as a linear combination of $$u^*_i$$. This makes it clear that the space of all possible linear functionals is also a vector space, which we call $$V\!\!^*$$, spanned by the basis set $$\{u^*_i\}$$.

This means that we have a straightforward mapping called the "dual", where the dual of a vector $$x$$ (where $$x$$ is from $$V$$) is a linear functional $$x^*$$ (where $$x^*$$ is from $$V\!\!^*$$). Very simply, $$u^*_i$$ are the duals of the basis vectors $$u_i$$. And to find the dual of any vector $$x$$, we express $$x$$ via the basis vectors $$u_i$$, and $$x^*$$ is similarly expressed via the dual vectors $$u^*_i$$.

Se we see that we can, as a notational shorthand, add the "star" symbol to a vector to represent that we went through this "dual" map. It's as easy as that. (In physics, e.g., quantum mechanics, we use the $$\dagger$$ symbol instead of the star, and we call it the Hermitian adjoint.)

Dualing duals
----------
So what can we deduce about the dual space of a dual space? To think about this, we apply the same reasoning as above, but now the dual space $$V\!\!^*$$ is simply considered to be a plain vector space. So we need to consider the linear functionals on $$x^*$$ from $$V\!\!^*$$, which are linear maps from $$x^*$$ to real numbers.


Let's take a step back. Take a look again at how we defined the basis vectors $$u^*$$:

$$
u^*_i(u_j) = \delta_{ij}.
$$

This is a linear map from $$u_j$$ to a real number, with the map parametrized by $$u^*_i$$:

$$
u_j \mapsto_{(u^*_i)} \alpha, \alpha \in \mathbb{R}.
$$

Via the reasoning above, we saw that such a linear map enabled us to generate the basis vectors $$u^*_i$$ of the dual space by simply adding a "star" symbol to the basis vectors $$u_i$$ of the original vector space.

But another way to look at the equation above is that this is a function machine that takes two inputs ($$u^*_i$$ and $$u_j$$) and produces a real number output. So it can be considered to be a map from $$u^*_i$$ to a real number, parametrized by $$u_j$$:

$$
u^*_i \mapsto_{u_j} \alpha, \alpha \in \mathbb{R}.
$$

Taking that as our inspiration, we define a new linear map:

$$
u^*_i(w_j) = \delta_{ij},
$$

where this linear map from $$u^*$$ to real numbers is parametrized by $$w_j$$:

$$
u^*_i \mapsto_{w_j} \alpha, \alpha \in \mathbb{R}.
$$


So this definitional linear map now enables us to generate the basis vectors of the dual space of $$V\!\!^*$$ by removing the "star" symbol and replacing "u" with "w". I.e., the dual of $$u^*_i$$ is simply $$w_i$$.

If we construct a new vector space spanned by $$w_i$$, we see that this new vector space is essentially the same, up to renaming $$u$$ with $$w$$, as the original base vector space $$V$$.

>The dual of a dual gets you back to the same space.


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111993699873026393){:target="_blank"}


[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimiters, and using $$ for the latex delimiters for both math mode and display math mode.)


