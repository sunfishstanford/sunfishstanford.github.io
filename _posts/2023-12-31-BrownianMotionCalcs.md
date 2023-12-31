---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'probability theory', math]
title: "Brownian motion and time travel"
permalink: /:year/:title:output_ext


# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimiters, and using $$ for the latex delimiters for both math mode and display math mode.)

The lecture notes from Jonathan Goodman (NYU Courant Institute) on stochastic calculus nicely complement the various stochastic calculus textbooks because the NYU lecture notes focus on applications instead of proofs. In [Lesson 1 on Brownian motion](https://math.nyu.edu/~goodman/teaching/StochCalc2018/notes/Lesson1.pdf){:target="_blank"}, there is a very interesting discussion of the intuition for forward and backward Kolmogorov equations. 

Gaussian kernel: transition probability for Brownian motion
-------
We begin with Eq. (2) in the lecture notes for the probability density function (PDF) of $$X_t$$ when the particle starts with $$x=0$$ at $$t=0$$:

$$
u(x,t) = \frac{1}{\sqrt{2 \pi \, t}} e^{-\frac{x^2}{2 t}}
$$

This is a Gaussian kernel (Green's function or impulse response) that gives the probability density at a later time for a starting delta function distribution. It is a function of only the change in position $$\Delta x$$ and the change in time. Also, it is an even function in $$\Delta x$$, which means that correlations and convolutions in $$\Delta x$$ look the same. From now on, we represent this as $$G(x,y,t)$$, where $$x$$ is replaced with $$x-y$$.

We then have Eq. (10), the PDF when given an arbitrary starting position:

$$
\displaystyle u(x,t)=\int_{-\infty}^{\infty} u_0(y)G(x,y,t)dy
$$

This is derived by convolving the Gaussian kernel with the starting distribution. If we set $$t=0$$, then the convolution with the Gaussian kernel is an identity operation because it is equivalent to evolving time over zero time. So we get back the initial condition $$u_0(x)$$; this is why we say it satisfies the Kolmogorov forward equation (see bottom of p. 5 of the lecture notes), as it starts with an initial distribution and calculates the impact of forward time evolution.

On the other hand, the value function in Eq. (7) is the conditional expectation of $$V(X)$$ at time $$T$$ given that $$X=x$$ at time $$t$$:

$$
f(x,t)=\frac{1}{\sqrt{2 \pi \, (T-t)}}\int_{-\infty}^{\infty}V(y)e^{-\frac{(x-y)^2}{2 (T-t)}}dy
$$

(I corrected the typo in the lecture notes—it should be $$V(y)$$.)

We can think of this as: start with a delta function centered at $$x$$ as the initial PDF of $$X$$ at time $$t$$ (“conditional on $$X_t=x$$”), then evolve forward to time $$T$$ using the Gaussian kernel to give the PDF of $$X_T$$, and finally use that as the probability measure over which to integrate $$V(X)$$ to give the expectation value of $$V(X_T)$$.

Evolving forward and backward in time
-------
*Here is the insight: while the PDF $$u(x,t)$$ is evolving forward in time, the conditional expectation $$f(x,t)$$ is evolving backward in time.*

If we plug in $$t=T$$ into $$f(x,t)$$, we get $$f(x,T) = V(x)$$, and therefore $$V(x)$$ is the final state of $$f(x,t)$$ at time $$T$$. Therefore, $$f(x,t)$$ is evolving backward in the sense that the expression for $$f(x,t)$$ is the convolution of a kernel (actually the backward kernel) *not* with the initial state at time zero, but *instead* with $$V(x)$$, which is the final state at time $$T$$. And this is why the value function $$f(x,t)$$ satisfies the Kolmogorov backward equation.

---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111672004708735800){:target="_blank"}


