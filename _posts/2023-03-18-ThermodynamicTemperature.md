---
layout: post
usemathjax: true
categories: [math, physics, 'embracing transitory confusion']
title: "Simple explanation of the thermodynamic temperature scale"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---


![Reversible engines](/assets/images/Carnot.png){: width="600" .center-image }

How to get thermodynamic temperature scale

Basic properties a temp scale should satisfy:

Consistent meaning of higher vs lower - should be consistent however you apply successive examples
Monotonically increasing function of any other valid temperature scale - this also ensures that it’s an invertible function, and satisfies property #1
Here’s how we define a temperature scale that naturally leads us to the definition of entropy

Start with a reference reservoir at a specific temp, call it one degree in our new units Pick a new reservoir with a higher temperature, consider a Carnot engine between those two temps; let the heat flow be $$Q_h$$ from the higher temp, and $$Q_l$$ into the lower temp Define the temperature of the new reservoir to be $$x$$ degrees, where $$x$$ is the ratio $$Q_h/Q_l$$

The Second Law of Thermodynamics tells us that for any two given temperatures, all Carnot engines connected to those two temperatures have the same efficiency, meaning that they have the same ratio of heat flows for the higher and lower temperatures.

Take any three reservoirs at temperatures $$T_1$$, $$T_2$$, and $$T_3$$, where $$T_1$$ is highest temp and $$T_3$$ is lowest temp. Consider case 1: a single Carnot engine between the $$T_1$$ and $$T_3$$ and heat flows $$Q_1$$ and $$Q_3$$, versus case 2: two Carnot engines A and B in series, with one engine between $$T_1$$ and $$T_2$$ and one between the $$T_2$$ and $$T_3$$. For Case 2, the two Carnot engines are sized so that engine A gets heat flow $$ Q_1 from T_ 1 and puts heat flow $$ Q_ 2A into T_ 2 and engine B gets heat flow $$ Q_ 2B from T_ 2 and puts heat flow $$ Q_ 3 into T_ 3$$. Then, since the ratio of heat flows for any Carnot engine between two temperatures is just the ratio of the temperatures (if we assume we use the temperature scale given above), we must have

\begin{equation} \frac{Q_{1}}{Q_{2A}} = \frac{T_{1}}{T_{2}} \end{equation}

\begin{equation} \frac{Q_{2B}}{Q_{3}} = \frac{T_{2}}{T_{3}} \end{equation}

---

[Comment on Mastodon](https://hachyderm.io/@Sunfishstanford/109960227623861947){:target="_blank"}
