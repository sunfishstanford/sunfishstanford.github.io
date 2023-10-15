---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'physics', math]
title: "Free Energy, Part II"
permalink: /:year/:title:output_ext

---

In [Part I of this post](https://freeenergy.blog/2023/FreeEnergy1.html){:target="_blank"}, we explained that the word "free" in "free energy" refers to the energy being available to do useful work. Here, we will dive in further to understand the rationale behind two different types of free energy, the [Helmholtz free energy $$F$$](https://en.wikipedia.org/wiki/Helmholtz_free_energy){:target="_blank"} and the [Gibbs free energy $$G$$](https://en.wikipedia.org/wiki/Gibbs_free_energy){:target="_blank"}. 

Why do we need different types of free energy? Why is Gibbs free energy restricted to non-pressure-volume work (AKA mechanical work)? We'll dive into this and more, but first we'll take a step back and think about the bigger picture and why we need to define the reservoir and the environment.

The Reservoir and the Client
--------
The Reservoir in a thermodynamic system is like the central bank in an economy. It sets the rules of the game. 

In thermodynamics, the Reservoir is an idealized object that is so large that adding or subtracting a small amount of energy will have a minimal impact on its temperature, and therefore we think of the reservoir as *dictating* a fixed temperature $$T$$ on a System that is in thermal contact. This is done by exchanging the appropriate amount of thermal energy (i.e., heat) between the Reservoir and the System to bring the System to the temperature $$T$$. In other words, heat flows freely between the Reservoir and the System to maximize total entropy, and the result is that the System's temperature becomes $$T$$.

We often want to analyze situations where a thermodynamic System, under the influence of a Reservoir, is also coupled to a third object. So it's convenient to define the "Client" as a third object that interacts with the System via energy exchanges that relate to useful work being performed. For example, the System could be an engine that transmits mechanical energy to the Client to enable water to be pumped; or, the System could be a battery that transmits electrical energy to the Client to enable computation to be performed.

Mediation of work and regulation of temperature
------------
Between any two thermodynamic objects, e.g., between the System and the Client, the performance of useful work is mediated via one or more extensive state variables changing under the influence of the conjugate intensive state variables. Some example:
- The System is a gas that pushes on a piston; the extensive variable is the volume and the conjugate intensive variable is pressure
- The System is a battery that pushes electrons through an external circuit by applying voltage “pressure” on the electrons; the extensive variable is electrical charge and the conjugate intensive variable is voltage

Similarly, the Reservoir can regulate (i.e., hold constant) an intensive variable of the System by coupling via the conjugate extensive variable. For example, if the System is interfaced to the Reservoir via a piston or a flexible membrane, so that a change in the Reservoir's volume is counterbalanced by an equal but opposite change in the System's volume (so that the total volume is constant), then the pressure in the System will be held constant by the Reservoir. Analogous to how temperature is held constant, here pressure is held constant by varying the volume of the System to bring the System to the pressure $$P$$. In general, for a pair of conjugate intensive/extensive variables, the Reservoir can be coupled to the System via the extensive variable, and this would cause the intensive variable of the System to be held constant.

When the Reservoir fixes the temperature of the System via a free exchange of thermal energy between the Reservoir and the System, the intensive variable being regulated is the temperature $$T$$. However, even though the coupling is via thermal energy, the conjugate extensive variable is *not* energy, but instead is the entropy $$S$$; unlike the pressure-volume example where the total volume is constant, here the total entropy is monotonically increasing due to the Second Law of Thermodynamics. 

All of this is summarized by the equation for the change in internal energy, 

$$
dU=TdS - PdV + \sum_i \mu_i n_i
$$

How to measured the relevant "free energy"
------------

With these big picture concepts clarified, we can now focus back on "free energy". If we are interested in a specific case where the System does work on the Client, then because that work is mediated by certain extensive and intensive variables, we will need to isolate the portion of $$dU$$ that relates to the relevant extensive and intensive variables. That portion is the change in free energy that is relevant to our case, and its integral would be the total work that has been done by the System on the Client. So we need a clever way to specify a “free energy” state variable as a function of $$U$$ and other state variables, such that the change in the free energy exactly corresponds to the work done by the relevant extensive and intensive variables.

So the Helmholtz free energy, $$F = U - TS$$, gives $$dF = -PdV$$ under the conditions of constant $$T$$ due to energy exchange with the reservoir, no constraint on $$P$$ from the reservoir, work done on the environment via $$PdV$$ (which means the pressure is the same for the system and the environment), and constant $$n$$ and other extensive variables. So if we want to calculate amount of work available for the system to do on the environment involving $$P$$ and $$V$$ (“pressure-volume mechanical work”) under those conditions, then $$F$$ is the right free energy to use.

The Gibbs free energy, $$G = U - TS + PV$$, gives $$dG = \mu dn$$, under the conditions of constant $$T$$ due to energy exchange with the reservoir, constant $$P$$ due to interaction with the reservoir via the volume $$V$$, work done on the environment via $$\mu dn$$, and constant values for the other extensive variables. So if we want to calculate amount of work available for the system to do on the environment involving $$\mu$$ and $$n$$ (“chemical work that is non-mechanical”) under those conditions, then $$G$$ is the right free energy to use. Other variations of $$G$$ can be used to calculate the amount of work available related to other types of intensive-extensive variable pairs such as electrical work, electrochemical work, etc.



---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111067078789655621){:target="_blank"}


