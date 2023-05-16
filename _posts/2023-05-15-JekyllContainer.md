---
layout: post
usemathjax: true
categories: [tech]
title: "Jekyll server running in a container on Apple silicon"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimeters, and using $$ for the latex delimiters for both math mode and display math mode.)

Due to my primitive skills, I had been using Github Pages as my markdown verifier, and would make some changes to a new post, push to the repo in Github, catch any errors (usually in mathjax related stuff, which would exhibit subtle differences if rendered on another editor compared to how Github Pages/Jekyll would render it), then rinse and repeat. Very cumbersome because Github rations out processing cycles, so each iteration takes several minutes instead of being instantaneous. So the natural solution seemed to be a local install of a Jekyll server on my Macbook Air, to quickly verify how a new post looks.

However, I quickly found out how difficult it is to install a Jekyll environment on a Macbook with Apple silicon (M2 in my case). Bascially it did not seem doable.

Also, related to that, I've had a lot of trouble installing and trying open source software due to trouble with installation, dependencies, etc. on the Mac. 

So the natural solution is to go to Docker containers to isolate the new installs, and use that to run a local Jekyll server to quickly verify how a new post looks.

But of course, that also turned out to be very difficult. I tried several tutorials and repos for containers with Jekyll, and each promised to be really easy, but would invariably fail for mysterious and diverse reasons. So I decided to start from scratch and build a minimalist Docker container with Jekyll that could render the mathjax correctly, and not worry about other style issues.

The good news was it worked! And it actually isn't that complicated.

Lessons Learned
----------------
Here are my key lessons learned (which is a euphemism for the things to got me stuck for a long time) as a noob:

- Not all linuxes work for this. Turns out that Alpine, although very nice and small, probably doesn't work. But Debian does!
- The `jekyll serve` command defaults to listening at localhost, `127.0.0.1`, which has always worked for me in the past for serving ReactJS pages, etc. But since we now have a container running on my host (host = my macbook), we need to use `jekyll serve --host 0.0.0.0` to enable it to listen to the host. This had me stuck for a LONG time...
- The various FAQs and tutorials for setting up a Jekyll server give `jekyll new <directory>` as the command to run, to set up the basic files and directories. But that only works if that directory is empty, and I want to mount my host directory holding my working posts, so that the Jekyll server can auto-regenerate. So this means I had to first let Jekyll generate a new directory that's empty and populate it, and then I had to mount/bind my real directory to that point. Turns out this could be nicely separated into roles for `Dockerfile` vs. `docker-compose.yml`.

Step-by-step Instructions
-----------

1. Create a new directory, populated only with `Dockerfile` and `docker-compose.yml` (see those two files below)
2. `cd` to that directory
3. Run the following commands:

```bash
docker build -t j-image5 .
docker compose up
```

4. Open [http://localhost:4000](http://localhost:4000) to view the document, and reload to view the regenerated version.


`Dockerfile`
------
```Dockerfile
# syntax=docker/dockerfile:1
# Start from a directory that only has this Dockerfile 
# and the docker-compose.yml file
# Run the following in that directory:
# docker build -t j-image .

FROM debian
WORKDIR /j-dir
RUN apt-get update
RUN apt-get install ruby-full build-essential -y
RUN export GEM_HOME="$HOME/gems"
RUN export PATH="$HOME/gems/bin:$PATH"
RUN gem install jekyll bundler

# create basic jekyll directories and files
RUN jekyll new myblog

# add mathjax support
RUN echo '\nmarkdown: kramdown' >> myblog/_config.yml
RUN mkdir myblog/_includes
RUN echo '<!-- for mathjax support -->{% if page.usemathjax %}<script type="text/x-mathjax-config">MathJax.Hub.Config({TeX: { equationNumbers: { autoNumber: "AMS" } }});</script><script type="text/javascript" async src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>{% endif %}' >> myblog/_includes/head.html
```

`docker-compose.yml`
----------
```yml
#
# from the same directory as the Dockerfile, where the only other file
# is this docker-compose.yml file, run:
# docker compose up
# then open http://localhost:4000

services:
  j-serve:
    container_name: j-cont
    image: j-image
    command: bash -c "cd myblog && bundle exec jekyll serve --host 0.0.0.0"
    ports:
      - 4000:4000
    volumes:
      - <Path-to-your-working-copy-of-posts>/_posts:/j-dir/myblog/_posts
      - <Path-to-your-working-copy-of-posts>/assets/images:/j-dir/myblog/assets/images
```


---

[Comment on Mastodon](https://hachyderm.io/@Sunfishstanford/110377025214843206){:target="_blank"}


