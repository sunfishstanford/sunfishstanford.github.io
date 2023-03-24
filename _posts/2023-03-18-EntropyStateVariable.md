---
layout: post
usemathjax: true
categories: [math, physics, 'embracing transitory confusion']
title: "Entropy is a state variable!"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimeters, and using $$ for the latex delimiters for both math mode and display math mode.)


In thermodynamics, we have state variables (e.g., temperature, pressure, volume) that are properties uniquely determined by the system's equilibrium state and not dependent on the prior history. We know this because of a very large number of experiments that measured those state variables using various sensors and gauges for temperature, pressure, volume, etc., and demonstrated that unique sets of state variables map to unique states. In other words, a large body of empirical evidence has led us to conclude that those quantities are state variables.

Thermodynamics also tells us that entropy is a state variable. However, we don't have a sensor that measures entropy directly. So how do we make sense of why entropy is a state variable?

The answer is that a quantity is a state variable if and only if it has a well defined gradient, such that the path integral of the gradient is only dependent on the start and end points and not dependent on the precise connecting path (see this [prior post](https://sunfishstanford.github.io/math/physics/embracing%20transitory%20confusion/2023/02/24/imperfectDifferential.html){:target="_blank"}). Such a gradient is called a *perfect differential*.

Therefore, we just need to show that entropy has a perfect differential. And to do that, we use the profound properties of a Carnot heat engine.

In a Carnot engine, there are two temperatures connected to the engine, and two heat flows at those two temperatures. As the Carnot engine is operated through its cycle, it traces a closed path through the state space. The state space path of the cycle is comprised of four parts, namely a high temperature part, a low temperature part, and two adiabatic parts where no heat flows into or out of the engine.

In the high temperature part, we calculate the total heat flow as 

$$
Q_H = \int\limits_1 \delta Q T_H
$$





$$
\begin{aligned}
\eta(T_1,T_2) &= \frac{\vert Q_1 \vert - \vert Q_2 \vert}{\vert Q_1 \vert}\\
&= 1-\frac{T_2}{T_1}
\end{aligned}
$$


---

[Comment on Mastodon](https://hachyderm.io/@Sunfishstanford/110048426302213407){:target="_blank"}

