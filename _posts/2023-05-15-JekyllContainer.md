---
layout: post
usemathjax: true
categories: [tech]
title: "Jekyll server running in a container on Apple silicon"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimeters, and using $$ for the latex delimiters for both math mode and display math mode.)

Due to my primitive skills, I had been using Github Pages as my markdown verifier, and would make some changes to a new post, push to the repo in Github, catch any errors (usually in mathjax related stuff, which would exhibit subtle differences if rendered on another editor compared to how Jekyll would render it), then rinse and repeat. Very cumbersome because Github rations out processing cycles, so each iteration takes several minutes. So the natural solution seemed to be a local install of a Jekyll server on my Macbook Air, to quickly verify how a new post looks.

However, I quickly found out how difficult it is to install a Jekyll environment on a Macbook with Apple silicon (M1 or M2). Bascially it seemed impossible.

Related to that, I've had a lot of trouble installing and trying open source software due to trouble with installation, dependencies, etc. So the natural solution is to go to Docker containers to isolate the new installs, and using that to run a local Jekyll server, to quickly verify how a new post looks.

But of course, that also turned out to be very difficult. I tried several tutorials and repos for containers with Jekyll, and each would fail for mysterious and usually different reasons. So I decided to start from scratch and build a minimalist Docker container with Jekyll that could render the mathjax correctly, and not worry about other style issues.

The good news was it worked! And it actually isn't that complicated.

Here are the key lessons learned (which is a euphemism for the things to got me stuck for a long time):
adam i am
a
b
c
d






---

[Comment on Mastodon](https://hachyderm.io/@Sunfishstanford/110076556293445667){:target="_blank"}



