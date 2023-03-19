---
layout: post
usemathjax: true
categories: [math, physics, 'embracing transitory confusion']
title: "The beauty of the thermodynamic temperature scale"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimeters, and using $$ for the latex delimiters for both math mode and display math mode.)

The efficiency of a Carnot heat engine is a universal property that directly follows from the laws of thermodynamics, and the beautiful reasoning behind it was a key triumph of physics in the 19th century. As [Feynman wrote, at the beginning of his Section 44-4](https://www.feynmanlectures.caltech.edu/I_44.html){:target="_blank"}:

>The efficiency of an ideal engine...to find this universal law...is one of the very beautiful pieces of reasoning in physics

That section of the *Feynman Lectures* is a must-read, to appreciate this beauty referred to by Feynman. In my case, however, I found that section pretty challenging and had to re-read it many times before I finally got it. So I would like to provide a simplified explanation that I hope retains the essence.

The main question is: what is the efficiency of a Carnot heat engine? We know (see my prior [post](https://sunfishstanford.github.io/math/physics/embracing%20transitory%20confusion/2023/03/01/CarnotEngine.html){:target="_blank"}) that the Second Law of Thermodynamics tells us that for any two given temperatures, all Carnot engines connected to those two temperatures have the same efficiency. This means that if you consider the heat flow between the Carnot engine and the first temperature reservoir, and compare that to the heat flow between the Carnot engine and the second temperature reservoir, the ratio of the two heat flows must be a value that only depends on the two temperatures and not on any other details of the Carnot engine. And so the question is: what exactly does the efficiency depend on the two temperatures?

To answer this, the main idea is to define a new, fundamental type of temperature scale, the *thermodynamic temperature scale*, that is universally defined and independent of any specific material or measurement device. Contrast this with the mercury temperature scale that is more familiar, where we measure the expansion of liquid mercury and use that as the temperature scale, which clearly is very much dependent on the specific properties of mercury.

Here's what we do: start with a reservoir at some specific reference temperature $$T_R$$ that we pick for convenience (and of course we would need to standardize this so that different organizations can agree on the temperature scale), and we define this reference temperature to be "one degree" in our thermodynamic temperature scale. We then take a new reservoir at a different temperature $$T_{new}$$ and consider a Carnot engine between those two temperatures. Let the heat flows be $$Q_{new}$$ from the new temperature $$T_{new}$$ and $$Q_R$$ from the reference temperature $$T_R=1$$. 

Then, the definition of the thermodynamic temperature is very simple: we define the thermodynamic temperature of the new reservoir to be $$T_{new} = \lvert Q_{new}/Q_R \rvert T_R$$, which simplifies to $$\lvert Q_{new}/Q_R \rvert$$. In other words, for any Carnot engine the ratio of thermodynamic temperatures is the same as the absolute value of the ratio of heat flows. So to measure the temperature of an unknown reservoir, we connect a Carnot engine between the unknown reservoir and the reference reservoir at $$T_R=1$$, we measure the heat flows $$Q_{new}$$ and $$Q_R$$, and the unknown temperature is then measured to be the ratio $$\lvert Q_{new}/Q_R \rvert$$.

Using the thermodynamic temperature scale, the efficiency of a Carnot engine operating between a higher temperature $$T_1$$ and a lower temperature $$T_2$$ is

\begin{equation}
\eta(T_1,T_2) &= \frac{\vert Q_1 \vert - \vert Q_2 \vert}{\vert Q_1 \vert}\\
&= 1-\frac{T_2}{T_1}
\end{equation}

We would like this measurement technique to yield consistent temperature values, irrespective of how we choose to designate the reference reservoir. This means that for a specific set of unknown reservoirs, if two experimenters each independently picks a reference reservoir and uses this technique to measure the temperatures of all the unknown reservoirs, they should obtain two sets of temperature values that are consistent up to a scaling factor, where the scaling factor is the ratio of the two reference reservoir temperatures.

To demonstrate this, let's take three reservoirs at temperatures $$T$$, $$T_{R1}$$, and $$T_{R2}$$, where $$T$$ is an unknown temperature and $$T_{R1}$$ and $$T_{R2}$$ are two different choices of reference temperatures. Consider these two cases:

- Case 1: a single Carnot engine between $$T$$ and $$T_{R1}$$ with respective heat flows $$Q$$ and $$Q_{R1}$$
- Case 2: two Carnot engines $$A$$ and $$B$$ in series, with one engine between $$T$$ and $$T_{R2}$$ and another engine between $$T_{R2}$$ and $$T_{R1}$$. 

For Case 2, we size the two Carnot engines to be consistent with Case 1, which means that engine $$A$$ has heat flow $$Q$$ from $$T$$ and heat flow $$Q_{R2A}$$ into $$T_{R2}$$; and engine $$B$$ has heat flow $$Q_{R2B}$$ from $$T_{R2}$$ and heat flow $$Q_{R1}$$ from $$T_{R1}$$. Then, since the ratio of heat flows for any Carnot engine between two temperatures is just the ratio of the thermodynamic temperatures, we must have

$$
\lvert \frac{Q}{Q_{R2A}} \rvert = \frac{T}{T_{R2}}
$$

and

$$
\lvert \frac{Q_{R2B}}{Q_{R1}} \rvert = \frac{T_{R2}}{T_{R1}}
$$

Therefore, multiplying the two equations together,

$$
\lvert \frac{Q}{Q_{R1}} \frac{Q_{R2B}}{Q_{R2A}} \rvert = \frac{T}/{T_{R1}}
$$

But we know for the Carnot engine of Case 1 that $$\lvert Q/Q_{R1} \rvert = T/T_{R1}$$. Therefore, we have $$\lvert Q_{R2B}/Q_{R2A}\rvert = 1$$. Therefore, given a Carnot engine of Case 1, we can always construct two Carnot engines $$A$$ and $$B$$ so that they are each sized to match the Carnot engine of Case 1 at the temperatures $$T$$ and $$T_{R1}$$, and furthermore so that they share a common value (up to a potential negative sign) of heat flow $$Q_{R2}$$ at $$T_{R2}$$. 

Therefore, if experimenter Alice measures the unknown temperature using a reference reservoir at $$T_{R1}$$ defined to be at 1 degree, the result in Alice's temperature scale would be $$T_{Alice} = \lvert Q/Q_{R1} \rvert$$. Similarly, experimenter Bob, using reference $$T_{R2}$$ defined to be at 1 degree, would measure in Bob's temperature scale $$T_{Bob} = \lvert Q/Q_{R2} \rvert$$. And you could always convert between the two temperature scales using the scaling factor $$\lvert Q_{R1}/Q_{R2} \rvert$$. Therefore we have the consistency that were looking for.


Let’s take a step back and think about what this means.

By using the ratios of heat flow of Carnot engines to define our ratio of temperatures, we see that due to the Second Law of Thermodynamics, 





give the efficiency formula
---

[Comment on Mastodon](https://hachyderm.io/@Sunfishstanford/109960227623861947){:target="_blank"}
