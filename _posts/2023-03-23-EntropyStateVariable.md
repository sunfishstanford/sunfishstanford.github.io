---
layout: post
usemathjax: true
categories: [math, physics, 'embracing transitory confusion']
title: "Entropy is a state variable!"
permalink: /:year/:title:output_ext

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimeters, and using $$ for the latex delimiters for both math mode and display math mode.)


In thermodynamics, we have state variables (e.g., temperature, pressure, volume) that are properties uniquely determined by the system's equilibrium state and not dependent on the prior history. We know this because of a very large number of experiments that measured those state variables using various sensors and gauges for temperature, pressure, volume, etc., and demonstrated that unique sets of state variables map to unique states. In other words, a large body of empirical evidence has led us to conclude that those quantities are state variables. In fact, we could say that the concepts of temperature, pressure, volume, etc. were invented precisely *because* they are state variables that are directly observable.

Thermodynamics also tells us that entropy is a state variable. However, we don't have a sensor that measures entropy directly. So how do we make sense of why entropy is a state variable?

The answer is that a quantity is a state variable if and only if it has a well defined gradient, such that the path integral of the gradient over a closed path is zero, for any arbitrary closed path (see this [prior post](https://freeenergy.blog/2024/imperfectDifferential.html){:target="_blank"}). Such a gradient is called a *perfect differential*.

Therefore, we just need to show that entropy has a perfect differential. And to do that, we use the profound properties of a Carnot heat engine.

In a Carnot engine, there are two temperatures connected to the engine, and two heat flows at those two temperatures. As the Carnot engine is operated through its cycle, it traces a closed path through the state space. The state space path of the cycle is comprised of four parts, namely a high temperature part, a low temperature part, and two adiabatic parts where no heat flows into or out of the engine.

Let's find the path integral of $$\delta Q / T$$ around the whole cycle, for a Carnot cycle operating in the forward direction with positive heat flow at the high temperature, positive work done on the external environment, and negative heat flow at the low temperature. In the two adiabatic parts of the cycle, the heat flow is zero, and therefore they do not contribute to the integral. 

In the high temperature part at temperature $$T_H$$, the integral of $$\delta Q / T$$ is

$$
\int\limits_{\rm High-temp} \frac{\delta Q}{T} = \frac{1}{T_H} \int\limits_{\rm High-temp} \delta Q = \frac{\lvert Q_H \rvert}{T_H}
$$

where $$Q_H$$ is the total heat flow during the high temperature part.

Similarly, in the low temperature part at temperature $$T_L$$, the integral of $$\delta Q / T$$ is

$$
\int\limits_{\rm Low-temp} \frac{\delta Q}{T} = \frac{1}{T_L} \int\limits_{\rm Low-temp} \delta Q = \frac{-\vert Q_L \rvert}{T_L}
$$

where $$Q_L$$ is the total heat flow during the low temperature part (the negative sign means that heat flows in the direction from the Carnot engine to the low temperature reservoir).

Therefore, because the thermodynamic temperature scale is defined such that the ratio of the temperatures is equal to the absolute value of the ratio of the heat flows (see this [prior post](https://freeenergy.blog/2023/ThermodynamicTemperature.html){:target="_blank"}), the path integral over the entire closed cycle is zero.

Since this holds true for any arbitrary Carnot engine cycle, and since any closed path in the state space can be expressed as a sum of Carnot cycles, we have shown that $$\delta Q/T$$ is a perfect differential. We call this perfect differential

$$
dS = \frac{\delta Q}{T}
$$

and its integral gives us the state variable $$S$$, which of course is the entropy of the system!!

---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/110076556293445667){:target="_blank"}



