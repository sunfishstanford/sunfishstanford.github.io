---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'probability theory', math]
title: "Filtration and Information"
permalink: /:year/:title:output_ext


# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimiters, and using $$ for the latex delimiters for both math mode and display math mode.)

In my [prior post on martingales]({% post_url 2023-05-29-Filtration %}){:target="_blank"}, we touched on the topic of filtrations and our information about the world. In this post, we will dive deeper into this.

In the current context, when we say "information about the world," we are referring to the various random variables and stochastic processes being considered and our information on the events based on them. For example, if we are dealt 5 cards from a deck and so far two cards have been dealt, we have information on the identities of those two cards, but do not yet have information about the identities of the three future cards. Because we are talking about stochastic processes, we are concerned with how this information will change as time moves forward. 

Since we always require the stochastic processes and random variables to be adapted to the filtration and/or to be measurable, we know that at time $$t$$, the $$\sigma$$-field $$\mathcal{F}_t$$ contains all possible events that contain information on everything that happened up until time $$t$$.

On the other hand, if there is a random variable that is not $$\mathcal{F}_t$$-measurable, which means that events corresponding to this random variable taking on a specific value are not members of $$\mathcal{F}_t$$, then this random variable must not yet have a value as of time $$t$$. In other words, we will need to wait until a future time in order to determine the value of the random variable.

So we see that there is a precise correspondence between the $$\sigma$$-field $$\mathcal{F}_t$$ and the set of all possible events that contain information on everything that happened up until time $$t$$. And this is why an expectation conditioned on $$\mathcal{F}_t$$ is equivalent to an expectation conditioned on the information up until time $$t$$. 





---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/110456093484306985){:target="_blank"}



