---
layout: post
usemathjax: true
categories: [math, physics, 'embracing transitory confusion']
title: "The beauty of the thermodynamic temperature scale"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

# Bing prompt:
# Convert the following text to latex format,  only putting the math equation parts between the latex delimeters, and using $$ for the latex delimiters for both math mode and display math mode. 

There is a universal law for the efficiency of a Carnot heat engine, and the beautiful reasoning behind it was a key triumph of physics in the 19th century. As [Feynman put it, at the beginning of his Section 44-4](https://www.feynmanlectures.caltech.edu/I_44.html){:target="_blank"}:

>The efficiency of an ideal engine...to find this universal law...is one of the very beautiful pieces of reasoning in physics

We should all carefully read that section of the *Feynman Lectures* so that we can appreciate this beauty that Feynman refers to. In my case, however, I found it pretty challenging and tried many times, getting stuck in various parts of the complexity, before I finally got it. So I would like to provide a simplified explanation that I hope retains the essence.

The main question is: what is the efficiency of a Carnot heat engine? We know (see my prior [post](https://sunfishstanford.github.io/math/physics/embracing%20transitory%20confusion/2023/03/01/CarnotEngine.html){:target="_blank"}) that the Second Law of Thermodynamics tells us that for any two given temperatures, all Carnot engines connected to those two temperatures have the same efficiency. This means that if you consider the heat flow between the Carnot engine and the first temperature reservoir, and compare that to the heat flow between the Carnot engine and the second temperature reservoir, the ratio of the two heat flows must be a value that only depends on the two temperatures and not on any other details of the Carnot engine. And so the question is: what is the precise dependence of the efficiency on the two temperatures?

The core of the solution is to define a new, fundamental type of temperature scale, the *thermodynamic temperature scale*, that is universally defined and independent of any specific material or measurement device. Contrast this with the mercury temperature scale that is more familiar, where we measure the expansion of liquid mercury and use that as the temperature scale, which clearly is very much dependent on the specific properties of mercury.

Here's what we do: we start with a reservoir at some specific temperature that we pick for convenience (and of course we would need to standardize this so that different organizations can agree on the temperature scale), and we define this to be "one degree" in our new temperature scale. We then take a new reservoir at a higher temperature (similar logic applies if the new temperature is lower) and consider a Carnot engine between those two temperatures. Let the heat flow be $$Q_H$$ from the higher temperature and $$Q_L$$ into the lower temperature (which is by definition at the thermodynamic temperature $$T_L=1$$). 

Then, the definition of the thermodynamic temperature is very simple: we define the thermodynamic temperature of the new reservoir to be $$T_H = (Q_H/Q_L) T_L$$, which is simply $$Q_H/Q_L$$. In other words, for any Carnot engine the ratio of thermodynamic temperatures is the same as the ratio of heat flows. So to measure the temperature of an unknown reservoir, we connect a Carnot engine between the reservoir and the reference reservoir at the temperature defined to be $$T_L=1$$, we measure the heat flows $$Q_H$$ and $$Q_L$$, and the unknown temperature is then measured to be the ratio $$|Q_H/Q_L|$$.

We would like this measurement technique to yield consistent values for temperature, no matter how we happened to pick the reference reservoir. So to think about this, let's take any three reservoirs at temperatures $$T_1$$, $$T_2$$, and $$T_3$$, where $$T_1$$ is the highest and $$T_3$$ is the lowest. Consider these two cases:

- Case 1: a single Carnot engine between $$T_1$$ and $$T_3$$ with respective heat flows $$Q_1$$ and $$Q_3$$
- Case 2: two Carnot engines $$A$$ and $$B$$ in series, with one engine between $$T_1$$ and $$T_2$$ and another engine between $$T_2$$ and $$T_3$$. 

For Case 2, the two Carnot engines are sized to be consistent with Case 1, which means that engine $$A$$ gets heat flow $$ Q_1$$ from $$T_ 1$$ and puts heat flow $$Q_ 2A$$ into $$T_ 2$$; and engine $$B$$ gets heat flow $$Q_ 2B$$ from $$T_ 2$$ and puts heat flow $$Q_ 3$$ into $$T_ 3$$. Then since the ratio of heat flows for any Carnot engine between two temperatures is just the ratio of the thermodynamic temperatures, we must have

$$
\frac{Q_{1}}{Q_{2A}} = \frac{T_{1}}{T_{2}}
$$

$$
\frac{Q_{2B}}{Q_{3}} = \frac{T_{2}}{T_{3}}
$$

Therefore, multiplying the two equations together,

$$
\frac{Q_1}{Q_3} \frac{Q_{2B}}{Q_{2A}} = \frac{T_1/T_3}
$$

But we know for the Carnot engine of Case 1 that $$Q_1/Q_3 = T_1/T_3$$. Therefore, we have $$Q_{2B}/Q_{2A} = 1$$. This means that we can iterate on this process and build up any arbitrary number of Carnot engines in series, with the lowest engine connected to the lowest temperature and the highest engine connected to the highest temperature, and at every intermediate temperature 

, and the net flow of heat is zero for the reservoir at $$T_2$$, no matter what we choose for $$T_1$$, $$T_2$$, and $$T_3$$. This means that from the perspective of the external environment, the two Carnot engines $$A$$ and $$B$$ in series (Case 1) is equivalent to a single Carnot engine (Case 2).

And we see that this is a self-consistent way to define temperature because if we happened to 


Let’s take a step back and think about what this means.

By using the ratios of heat flow of Carnot engines to define our ratio of temperatures, we see that due to the Second Law of Thermodynamics, 





give the efficiency formula
---

[Comment on Mastodon](https://hachyderm.io/@Sunfishstanford/109960227623861947){:target="_blank"}
