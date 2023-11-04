---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'probability theory', math]
title: "Confusion about martingales in stochastic processes"
permalink: /:year/:title:output_ext

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimiters, and using $$ for the latex delimiters for both math mode and display math mode.)

I started to learn about stochastic calculus because I think many of the most interesting breakthroughs these days (e.g., [diffusion probabilistic models for generative AI](https://www.quantamagazine.org/the-physics-principle-that-inspired-modern-ai-art-20230105/){:target="_blank"}) involve stochastic processes. Much of the math here is unfamiliar to me with my traditional physics background, and it's been fun and also very confusing learning about Lebesgue integrals, measure theory, sigma algebras and Borel sets, rigorous probability theory, etc. For example, even though I thought I knew what random variables are, learning the rigorous definition of random variables has really helped me to understand them more deeply.

As I started down this journey, I soon came across the really interesting concept of **martingales**. Just trying to understand the definition of a martingale was very confusing for me!

A [discrete-time martingale](https://en.wikipedia.org/wiki/Martingale_(probability_theory)#Definitions){:target="_blank"} $$X_t$$ is commonly defined as a stochastic process that satisfies:

$$
E(X_{t+1} \mid X_1, . . . , X_t) = X_t
$$

or

$$
E(X_{t+1} \mid \mathcal{F}_t) = X_t.
$$

Here, $$\{X_1,...,X_{t+1},...\}$$ is a stochastic process that is a sequence of random variables, and the [filtration $$\mathbb{F}$$](https://www.worldscientific.com/worldscibooks/10.1142/p821#t=aboutBook){:target="_blank"} is a family $$\{\mathcal{F}_t\}$$ of increasing $$\sigma$$-fields (*aka* $$\sigma$$-algebras to mathematicians) that specifies how information is revealed in time.

My points of confusion...
--------
- We know that a conditional expectation is a random variable. But if the conditional expectation on the left is conditioned on $$X_t$$ (among other things) and the martingale definition requires it to be equal to $$X_t$$, then since $$X_t$$ is given, how can it still be a random variable that is not deterministic?

- Why does $$\mathcal{F}_t$$ represent our knowledge at time $$t$$ (i.e., equivalent to the knowledge of the random variables up through $$X_t$$)? We know that $$\mathcal{F}_t$$ is a $$\sigma$$-field that contains all possible events where $$x_1...x_t$$ are known and $$x_{t+1}...$$ are undetermined. In other words, $$\mathcal{F}_t$$ does not impose a specific set of values for $$x_1...x_t$$. So at time $$t$$, if we actually know the specific set of values for $$x_1...x_t$$ because those samples have already been drawn, isn't that more knowledge than what $$\mathcal{F}_t$$ contains?

- If $$\{X_t\}$$ is adapted to the filtration $$\mathbb{F} = \{\mathcal{F}_t\}$$, then $$X_{t+1}$$ is $$\mathcal{F}_{t+1}$$-measurable. But this means that $$X_{t+1}$$ is *not* $$\mathcal{F}_t$$-measurable. So then how can we compute $$E(X_{t+1} \mid \mathcal{F}_t)$$?


...and why it actually all makes sense!
---------

### Random variables versus deterministic quantities
When we have an expectation $$E(\cdot \mid X_t)$$ conditional on a random variable $$X_t$$, it means that for each possible value $$x_t$$ of $$X_t$$, there is a corresponding set of outcomes $$\{X_t=x_t\}$$ that the random variable maps to that value (remember that a random variable is a function that maps from an outcome to a real number), and we compute the expectation value via a weighted average over that set. So we can view the conditional expectation as a function of $$x_t$$. In other words, saying that we are "given $$X_t$$" does not mean that $$X_t$$ is fixed and deterministic; it's kind of like calling it "expectation assuming $$X_t$$".

### Knowledge at time $$t$$
I was confusing the sample values $$x_1...x_t$$ (which take on specific values as of time $$t$$) with the random variables $$X_1...X_t$$ (which do not dictate specific values). Remember that $$X_t$$ is a random variable that maps from each outcome to a specific value of $$x_t$$. Therefore, in the context of an expectation conditioned on $$X_t$$ or conditioned on $$\mathcal{F}_t$$, both $$X_t$$ and $$\mathcal{F}_t$$ enable us to map from an outcome (where each outcome is an element of $$\Omega$$ in the probability space $$(\Omega, \mathcal{F}, \mathcal{P})$$) to an event contained inside $$\mathcal{F}_t$$, and to use that event to compute the average value of the expectation. So these two types of conditional expectations produce the same random variable as the result. And just like it is with $$\mathcal{F}_t$$, the random variable $$X_t$$ does not impose a specific value for $$x_t$$. So when we say "knowing $$X_t$$ means that we know what has happened up through time $$t$$", we mean that if we do many experiments, in each experiment we know a specific outcome that drove $$X_1...X_t$$ to take a specific set of value for $$x_1...x_t$$, and in that sense we know what has happened up through time $$t$$. And this is exactly why we can say that "$$\mathcal{F}_t$$ specifies our available information up through time $$t$$".

### $$X_{t+1}$$ not $$\mathcal{F}_t$$-measurable
This one turned out to be a red herring. $$X_{t+1}$$ is certainly not $$\mathcal{F}_t$$-measurable. Every event within $$\mathcal{F}_t$$ contains outcomes where $$X_{t+1}$$ takes on different values. However, this does not stop us from computing $$E(X_{t+1} \mid \mathcal{F}_t)$$. We simply take a weighted average of $$X_{t+1}$$ over each event within $$\mathcal{F}_t$$. No big deal, nothing broken...


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/110456093484306985){:target="_blank"}



