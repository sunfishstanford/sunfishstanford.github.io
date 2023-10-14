---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'physics', math]
title: "Free Energy, Part II"
permalink: /:year/:title:output_ext

---

(In [Part I of this post](https://freeenergy.blog/2023/FreeEnergy1.html){:target="_blank"}, we explained that the word "free" in "free energy" refers to the energy being available to do useful work.) 

There are various flavors of free energy, and the two most well known are the [Helmholtz free energy $$F$$](https://en.wikipedia.org/wiki/Helmholtz_free_energy){:target="_blank"} and the [Gibbs free energy $$G$$](https://en.wikipedia.org/wiki/Gibbs_free_energy){:target="_blank"}. 

We've probably all have seen their definitions before. But why do we need these different types of free energy? And how do they relate to pressure-volume work (AKA mechanical work)?

The change in internal energy $$dU=TdS - PdV + \mu dn + \dots$$, is expressed in terms of various intensive and extensive variables. In general, the system will exchange energy with the outside (the outside can be defined to consist of the “environment” plus the “reservoir”, where the environment means something outside that we want to analyze, such as a computing system that consumes energy; and the reservoir means everything else in the universe, which is so large that we think of it as being at a constant temperature). For a given system and environment, the exchange in energy is mediated via some extensive variable changing under the influence of an intensive variable. For example, if the system is a gas that pushes on a piston, then the extensive variable is the volume and the intensive variable is pressure. If the system is a battery that pushes electrons through an external circuit by applying voltage “pressure” on the electrons, then the extensive variable is electrical charge and the intensive variable is voltage.  if we are interested in how the system does work on its environment (or equivalently, how its environment does work on the system), then we want to isolate the portion of dU that relates to the relevant extensive and intensive variable. If we could do that, we call that portion the change in free energy that is relevant to our situation, because the integral of that free energy would let us calculate how much total work has been done between the system and the environment. So we need a clever way to specify a “free energy” state variable that is specified in terms of $$U$$ and other state variables, such that the change in the free energy exactly corresponds to the desired work done.

So the Helmholtz free energy, $$F = U - TS$$, gives $$dF = -PdV$$ under the conditions of constant $$T$$ due to energy exchange with the reservoir, no constraint on P from the reservoir, work done on the environment via PdV (which means the pressure is the same for the system and the environment), and constant n and other extensive variables. So if we want to calculate amount of work available for the system to do on the environment involving P and V (“P-V mechanical work”) under those conditions, then F is the right free energy to use.

The Gibbs free energy, $$G = U - TS + PV$$, gives $$dG = \mu dn$$, under the conditions of constant T due to energy exchange with the reservoir, constant P due to interaction with the reservoir via the volume V, work done on the environment via $$\mu dn$$, and constant values for the other extensive variables. So if we want to calculate amount of work available for the system to do on the environment involving $$\mu$$ and $$n$$ (“chemical work that is non-mechanical”) under those conditions, then G is the right free energy to use. Analogous versions of G can be used to calculate the amount of work available related to other types of intensive-extensive variable pairs such as electrical work, electrochemical work, etc.



---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111067078789655621){:target="_blank"}


