---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'probability theory', math]
title: "Confusion about conditional probabilities"
permalink: /:year/:title:output_ext



# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab

---
The [conditional probability of event A given event B](https://en.wikipedia.org/wiki/Conditional_probability){:target='_blank'} is a very important concept that seems straightforward. "If I know that B has occured, what is the probability that A has occured?" 

However, a few points of confusion came up as I learned about generative models and conditional probabilities (see [this post](https://freeenergy.blog/2024/EMnotes.html){:target='_blank'}).

What confused me
--------

If $$x$$ is a vector in the space of images and $$z$$ is a vector in the latent space of the image classifications, and if we want to generate an image of a rose, then we need to sample from the conditional probability distribution $$x \sim P(x \mid z_0)$$, where $$z_0$$ is the category "rose".

But we know that the conditional probability can be expressed as

$$
P(x \mid z) = \frac{P(x,z)}{P(z)}. \label{eq:1} 
$$

So let's assume that we are given the joint probability density $$P(x,z)$$, because that is determined by how the images fit into the various classification and should not depend on our arbitrary choice of a rose image. Then, since we decided to generate a rose image, which means that $$z$$ is definitely the rose value $$z_0$$, we need to set $$P(z)$$ to be a delta function at $$z_0$$. But $$P(z)$$ is supposed to be the marginal distribution, calculated by integrating $$P(x,z)$$ over $$x$$, so it cannot be affected by our arbitrary choice of $$z_0$$. So there is a contradiction...



And why it actually makes sense
--------

Here's where I went wrong: the joint distribution fully determines the marginal distribution. So we are not allowed to arbitrarily specify both the joint distribution $$P(x,z)$$ and the marginal distribution $$P(z)$$. And there are two approaches to thinking about this.

In the first approach, if we assume that there is a "global truth", a joint distribution $$P(x,z)$$ that is valid for any choice of $$z$$, then $$P(z)$$ is the probability that a randomly sampled image has the classification of $$z$$, and *has nothing to do with whether or not we decided to generate a rose image*. So it is INCORRECT to set $$P(z)$$ to be a delta function at $$z_0$$. The correct method is to take $$P(x,z)$$, divide it by $$P(z)$$ (which is calculated by marginalizing $$P(x,z)$$ over $$x$$), and evaluate the quotient at $$z=z_0$$.

In the second approach, we assume that the state of the world has evolved so that $$z=z_0$$ in the current state of the world. Then, $$P(z)$$ would indeed be a delta function at $$z_0$$. And $$P(x,z)$$ would have evolved so that when you marginalize it over $$x$$ (i.e., $$\int P(x,z) dx = P(z)$$), we get a $$P(z)$$ that says that the event $$z=z_0$$ occurs with certainty.


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111864185348155125){:target="_blank"}


[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimiters, and using $$ for the latex delimiters for both math mode and display math mode.)


