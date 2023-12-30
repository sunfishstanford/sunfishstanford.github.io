---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'probability theory', math]
title: "Filtration and Information"
permalink: /:year/:title:output_ext


# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimiters, and using $$ for the latex delimiters for both math mode and display math mode.)

In my prior posts on [martingales]({% post_url 2023-05-29-Filtration %}){:target="_blank"} and [visualizing martingales]({% post_url 2023-12-27-VisualizingMartingales %}){:target="_blank"}, we touched on the topic of filtrations and our information about the world. In this post, we will dive a bit deeper.

In the current context, when we say "information about the world," we are referring to the various random variables and stochastic processes being considered and our information on the events defined by the possible measurement results from the stochastic processes. For example, if we plan to randomly draw 5 cards from a deck and so far two cards have been drawn, we have "measured the results" for the first two cards drawn, which means that we know the identities of those two cards, but we would not yet know the identities of the three future cards. (For a real deck of cards, we *would* have information on the three future cards based on the first two cards drawn, but that is a different topic outside the scope here.) Because we are talking about stochastic processes, we are concerned with how this information will change and how it relates to the filtration as time moves forward. 

### Knowledge at time $$t$$

Since we always require the stochastic processes/random variables to be adapted to the filtration (equivalently, to be $$\mathcal{F}_t$$-measurable), at time $$t$$ the $$\sigma$$-field $$\mathcal{F}_t$$ contains all events that are known as of that time to be either true or false. This means that even though there remain future measurements of random variables at later times, those future measurement results would not change the "true vs. false" status of each of the events contained in $$\mathcal{F}_t$$; their fates have been sealed as of time $$t$$. Before time $$t$$, we *did not* know whether each event in $$\mathcal{F}_t$$ is true or false. At time $$t$$ and thereafter, we *do* know whether each event is true or false. And that's why $$\mathcal{F}_t$$ specifies our available information up through time $$t$$. 

Each event $$A \in \mathcal{F}_t$$ is a set of possible elementary outcomes $$\omega$$, where $$\omega \in \Omega$$ and $$\Omega$$ is the sample space. If at time $$t$$ we know that event $$A$$ is true, that means we know that $$\omega_{reality} \in A$$, where the elementary outcome $$\omega_{reality}$$ is
the actual state of the world. If there is another event $$A_1 \subset A$$ that is *NOT* a member of $$\mathcal{F}_t$$, it means that as of time $$t$$ we have not yet measured the random variables required to decide whether $$\omega_{reality} \in A$$ or $$\omega_{reality} \notin A$$. So as of time $$t$$, although we *do* know whether $$A$$ is true or false, we *do not* yet have sufficient information to determine whether $$A_1$$ is true or false.

And so a more precise statement is: "$$\mathcal{F}_t$$, together with the information it contains at time $$t$$, which means the knowledge of the true/false nature of all events it contains, fully specifies our available information up through time $$t$$."


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111672004708735800){:target="_blank"}


