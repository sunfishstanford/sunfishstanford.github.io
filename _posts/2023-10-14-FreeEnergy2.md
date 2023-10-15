---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'physics', math]
title: "Free Energy, Part II"
permalink: /:year/:title:output_ext

---

In [Part I of this post](https://freeenergy.blog/2023/FreeEnergy1.html){:target="_blank"}, we explained that the word "free" in "free energy" refers to the energy being available to do useful work. Here, we will dive in further to understand the rationale behind two different types of free energy, the [Helmholtz free energy $$F$$](https://en.wikipedia.org/wiki/Helmholtz_free_energy){:target="_blank"} and the [Gibbs free energy $$G$$](https://en.wikipedia.org/wiki/Gibbs_free_energy){:target="_blank"}. 

Why do we need different types of free energy? And why is Gibbs free energy restricted to non-pressure-volume work (AKA mechanical work)? We will dive into this, but first we'll take a step back and think about the bigger picture and why we need to define a reservoir and the environment.

The Reservoir
--------
The Reservoir in a thermodynamic system is like the central bank in an economy. It sets the rules of the game. 

In thermodynamics, the Reservoir is an idealized object that is so large that adding or subtracting a small amount of energy will have a minimal impact on its temperature, and therefore we think of the reservoir as *dictating* a fixed temperature $$T$$ on a System that is in thermal contact. This is done by exchanging the right amount of energy between the Reservoir and the System to bring the System to the temperature $$T$$.

The Reservoir could also enforce other constraints on the System. For example, if the System is interfaced to the Reservoir via a piston or a flexible membrane, so that a change in the Reservoir's volume is counterbalanced by an equal but opposite change in the System's volume, then the pressure in the System will be held constant by the Reservoir. Analogous to how temperature is held constant, here this is done by varying the volume of the System to bring the System to the pressure $$P$$.

The Environment
-------------
We often want to analyze situations where a thermodynamic System, under the influence of a Reservoir, is furthermore coupled to a third object to exchange work energy. For example, the System could be an engine, and the third object could be a water pump. So it's useful to define the "Environment" as a third object that interacts with the System via energy exchanges that relate to useful work being performed. 

In general, the system will exchange energy with the outside (the outside can be defined to consist of the “environment” plus the “reservoir”, where the environment means something outside that we want to analyze, such as a computing system that consumes energy; and the reservoir means everything else in the universe, which is so large that we think of it as being at a constant temperature).

The change in internal energy $$dU=TdS - PdV + \mu dn + \dots$$, is expressed in terms of various intensive and extensive variables.  

For a given system and environment, the exchange in energy is mediated via some extensive variable changing under the influence of an intensive variable. For example, if the system is a gas that pushes on a piston, then the extensive variable is the volume and the intensive variable is pressure. If the system is a battery that pushes electrons through an external circuit by applying voltage “pressure” on the electrons, then the extensive variable is electrical charge and the intensive variable is voltage.  In general, for a pair of conjugate intensive/extensive thermodynamic state variables, the Reservoir can be coupled to the System via the extensive variable, and the results would be to hold the intensive variable at a constant value. Some examples include chemical potential/molar quantity and voltage/charge.

If we are interested in how the system does work on its environment (or equivalently, how its environment does work on the system), then we want to isolate the portion of dU that relates to the relevant extensive and intensive variable. If we could do that, we call that portion the change in free energy that is relevant to our situation, because the integral of that free energy would let us calculate how much total work has been done between the system and the environment. So we need a clever way to specify a “free energy” state variable that is specified in terms of $$U$$ and other state variables, such that the change in the free energy exactly corresponds to the desired work done.

So the Helmholtz free energy, $$F = U - TS$$, gives $$dF = -PdV$$ under the conditions of constant $$T$$ due to energy exchange with the reservoir, no constraint on $$P$$ from the reservoir, work done on the environment via $$PdV$$ (which means the pressure is the same for the system and the environment), and constant $$n$$ and other extensive variables. So if we want to calculate amount of work available for the system to do on the environment involving $$P$$ and $$V$$ (“pressure-volume mechanical work”) under those conditions, then $$F$$ is the right free energy to use.

The Gibbs free energy, $$G = U - TS + PV$$, gives $$dG = \mu dn$$, under the conditions of constant $$T$$ due to energy exchange with the reservoir, constant $$P$$ due to interaction with the reservoir via the volume $$V$$, work done on the environment via $$\mu dn$$, and constant values for the other extensive variables. So if we want to calculate amount of work available for the system to do on the environment involving $$\mu$$ and $$n$$ (“chemical work that is non-mechanical”) under those conditions, then $$G$$ is the right free energy to use. Other variations of $$G$$ can be used to calculate the amount of work available related to other types of intensive-extensive variable pairs such as electrical work, electrochemical work, etc.



---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111067078789655621){:target="_blank"}

