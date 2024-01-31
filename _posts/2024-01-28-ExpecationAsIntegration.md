---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'probability theory', math]
title: "Expected value is the same as (Lebesgue) integration"
permalink: /:year/:title:output_ext


# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab

# note: replace \b with \mathbf, if I decide to use \mathbf
---
Conventional definition
----------

For a discrete random variable $$X$$ the [expected value is defined as](https://en.wikipedia.org/wiki/Expected_value#Random_variables_with_finitely_many_outcomes){:target="_blank"}

$$
\begin{equation}
E[X] = \sum_{i\ \ \ \ } x_i P_{x_i},
\end{equation}
$$

where the sum is over all indexes $$i$$, and $$P_{x_i}$$ is the probability of $$x_i$$.


$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$

Similarly, for a continuous random variable $$X$$ that takes on real values, the [expected value is defined as](https://en.wikipedia.org/wiki/Expected_value#Random_variables_with_density){:target="_blank"}

$$
E[X] = \int\limits_{-\infty}^{\infty} x P(x) dx
$$




---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111677727136310287){:target="_blank"}

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimiters, and using $$ for the latex delimiters for both math mode and display math mode.)
