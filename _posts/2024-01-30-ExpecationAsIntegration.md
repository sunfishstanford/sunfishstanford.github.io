---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'probability theory', math]
title: "Expected value is the same as (Lebesgue) integration"
permalink: /:year/:title:output_ext


# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab

# note: replace \b with \mathbf, if I decide to use \mathbf
---

Surely obvious if you know probability theory well, but it took me a while to realize: 

`The expected value of a random variable (or of a function of a random variable) is the same as the Lebesgue integral of the random variable (or of the function thereof) over the probability measure.`

This is why the following are equivalent statements:

- $$X$$ is integrable
- The expected value of $$X$$ exists and is well defined

Conventional definition
----------

For a discrete random variable $$X$$ the [expected value is defined as](https://en.wikipedia.org/wiki/Expected_value#Random_variables_with_finitely_many_outcomes){:target="_blank"}

$$
\begin{equation}
E[X] = \sum_{i\ \ \ \ } x_i P_{x_i},
\end{equation}
$$

where the sum is over all indexes $$i$$, and $$P_{x_i}$$ is the probability of $$x_i$$.

Similarly, for a continuous random variable $$X$$ that takes on real values, the [expected value is defined as](https://en.wikipedia.org/wiki/Expected_value#Random_variables_with_density){:target="_blank"}

$$
E[X] = \int\limits_{-\infty}^{\infty} x P(x) dx.
$$

Lebesgue integral interpretation
-----

But this is just the Lebesgue integral of $$X$$ over the probability measure:

$$
E[X] = \int X dP.
$$

To see this, it's easier to consider the prior form:

$$
E[X] = \int\limits_{-\infty}^{\infty} x P(x) dx.
$$

Partition the range of $$X$$ into intervals; for each interval we multiply (1) the measure of the event mapped by the random variable $$X$$ into that interval (this corresponds to $$P(x)dx$$) with (2) the expression to be integrated (here it is $$X$$ because we are integrating $$X$$); sum over all intervals; and take the limit as the partition is made more finely.


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111848900096912297){:target="_blank"}


[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimiters, and using $$ for the latex delimiters for both math mode and display math mode.)
