---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'physics', math]
title: "Free Energy, Part II"
permalink: /:year/:title:output_ext

---

In [Part I of this post](https://freeenergy.blog/2023/FreeEnergy1.html){:target="_blank"}, we explained that the word "free" in "free energy" refers to the energy being available to do useful work. Here, we will dive in further to understand the rationale behind two different types of free energy, the [Helmholtz free energy $$F$$](https://en.wikipedia.org/wiki/Helmholtz_free_energy){:target="_blank"} and the [Gibbs free energy $$G$$](https://en.wikipedia.org/wiki/Gibbs_free_energy){:target="_blank"}. 

Why do we need different types of free energy? Why is Gibbs free energy restricted to non-pressure-volume work (AKA mechanical work)? We will dive into this, and along the way we'll also discuss the Reservoir and the Client, and how their interactions with the System affect the various energies and thermodynamic state variables.

TL;DR
-----
>Suppose that $$YdX$$ is an intensive/extensive pair used to store energy in the System. By integrating it over whatever process we go through, we would obtain the total energy that has been stored in the System by the Client, or equivalently, the total energy that is available by the "battery" System to discharge back to the Client. More precisely, this is the maximum amount of energy available to be discharged back to the Client assuming zero losses. We call this the "free energy" because it is available to be charged/discharged and is not bound to the System + Reservoir. So we need a clever way to specify a “free energy” state variable, such that the change in this "free energy state variable" is equal to $$YdX$$.

The Reservoir and the Client
--------
The Reservoir in a thermodynamic system is like the central bank in an economy. It sets the rules of the game. 

In thermodynamics, the Reservoir is an idealized object that is so large that adding or subtracting a small amount of energy will have a minimal impact on its temperature, and therefore we think of the reservoir as *dictating* a fixed temperature $$T$$ on a System that is in thermal contact. This is done by exchanging the appropriate amount of thermal energy (i.e., heat) between the Reservoir and the System to bring the System to the temperature $$T$$. In other words, heat flows freely between the Reservoir and the System to maximize total entropy, and the result is that the System's temperature becomes $$T$$.

We often want to analyze situations where a thermodynamic System, under the influence of a Reservoir, is also coupled to a third object. So it's convenient to define the "Client" as a third object that interacts with the System via energy exchanges that relate to useful work being performed. For example, the System could be an engine that transmits mechanical energy to the Client to enable water to be pumped; or, the System could be a battery that transmits electrical energy to the Client to enable computation to be performed.

Work, pressure, and temperature
------------
Between any two thermodynamic objects, e.g., between the System and the Client, the performance of useful work is mediated via one or more extensive state variables changing under the influence of the conjugate intensive state variables. Some examples:
- The System is a gas that pushes on a piston; the extensive variable is the volume and the conjugate intensive variable is pressure
- The System is a battery that pushes electrons through an external circuit by applying voltage “pressure” on the electrons; the extensive variable is electrical charge and the conjugate intensive variable is voltage

The interpretation of this interaction as a "battery that stores energy" is very fruitful, and depends on the interplay between the conjugate variables having the following characteristics:
1. The intensive variable is a type of "pressure" and the extensive variable is a type of "volume", so that the "pressure" seeks to push the "volume" towards an equilibrium point where the "pressure" has the same value in both the System and the Client. For example, if the System is interfaced to the Client via a piston or a flexible membrane, then the pressure will be equalized across the System and the Client. This serves to regulate the intensive variables on the two bodies to be equal to each other.
2.  When the extensive variable changes by a small amount, the product of its change with the intensive variable (e.g., "$$PdV$$") corresponds to a small amount of work being performed on each other by the two bodies.
3. The extensive variables in the System and the Client change in equal and opposite directions. This combined with #1 and #2 above means that every small reduction of energy in one body will be combined with an equal and opposite increase in energy in the other body. Therefore, this interplay between conjugate variables is equivalent to some energy sloshing back and forth, which enables the charging and discharging of a battery.

This "energy storage" dynamic between the conjugate variables can also serve as a "regulation" dynamic in the context of the System coupling to the Reservoir. Here, we are not interested in the work being done by those two bodies, but instead want to use the Reservoir to regulate an intensive variable of the System via characteristic #1 above. In general, for a pair of conjugate intensive/extensive variables, the Reservoir can be coupled to the System via the extensive variable, and this would cause the intensive variable of the System to be held constant.

When the Reservoir regulates the temperature of the System via a free exchange of thermal energy between the Reservoir and the System, the intensive variable being regulated is the temperature $$T$$. However, even though the coupling is via thermal energy, the conjugate extensive variable is *not* energy, but instead is the entropy $$S$$. Unlike the pressure-volume example where the total volume is constant, here the total entropy is monotonically increasing due to the Second Law of Thermodynamics. 

All of this is summarized by the equation for the change in internal energy of the System, 

$$
dU=TdS - PdV + \sum_i \mu_i dn_i \tag{1}\label{eq:U}
$$

How to measure the relevant "free energy"
------------

With these big picture concepts clarified, we can now focus back on "free energy". 

For any specific thermodynamic System, with a variety of intensive/extensive variables that relate to mechanical energy, electrical energy, electrochemical energy, etc., we can write an expression for the change in internal energy $$U$$ (Eq. $$\eqref{eq:U}$$) that reflects those elements.

The change in $$U$$ is composed of the first term $$TdS$$, which interacts with the Reservoir to hold the temperature $$T$$ constant, plus additional intensive/extensive pairs with the form $$YdX$$, where $$Y$$ is an intensive variable and $$dX$$ is the change in an extensive variable (mnemonic: "X is eXtensive"). (Due to our sign conventions, the pressure-volume term has a negative sign, written as $$-PdV$$.) Some of these intensive/extensive pairs of the System are used to couple with the Reservoir for regulation, and the rest of the intensive/extensive pairs are used to store energy (where the System is regarded as a battery that stores energy from the Client).

Suppose that $$YdX$$ is an intensive/extensive pair used to store energy in the System. By integrating it over whatever process we go through, we would obtain the total energy that has been stored in the System by the Client, or equivalently, the total energy that is available by the "battery" System to discharge back to the Client. More precisely, this is the maximum amount of energy available to be discharged back to the Client assuming zero losses. We call this the "free energy" because it is available to be charged/discharged and is not bound to the System + Reservoir. So we need a clever way to specify a “free energy” state variable, such that the change in this "free energy state variable" is equal to $$YdX$$.

In the case of the Helmholtz free energy, $$F = U - TS$$, we see that 

$$
dF = -SdT-PdV+ \sum_i \mu_i dn_i
$$ 

which simplifies to

$$
dF = -PdV+ \sum_i \mu_i dn_i
$$

under constant temperature. As we discussed above, this means that in Eq. $$\eqref{eq:U}$$ the $$TdS$$ term is coupled to the Reservoir to regulate temperature, and all of the other intensive/extensive pairs are coupled to the Client to store energy in the System. Therefore, $$F$$ is the free energy under these conditions.

The Gibbs free energy, $$G = U - TS + PV$$, gives

$$
dG = -SdT +VdP + \sum_i \mu_i dn_i
$$

which simplifies to

$$
dG = \sum_i \mu_i dn_i
$$

under the conditions of constant $$T$$ and constant $$P$$. This means that the $$TdS$$ term is coupled to the Reservoir to regulate temperature, the $$-PdV$$ term is coupled to the Reservoir to regulate pressure, and the remaining intensive/extensive pairs are coupled to the Client to store energy in the System. Therefore, $$G$$ is the free energy under these conditions.

And finally, note that for conditions where the Gibbs free energy is used, namely where $$T$$ and $$P$$ are held constant by the Reservoir, the $$-PdV$$ term is coupled to the Reservoir and not used to store energy. And so we say that the [Gibbs free energy is the energy that is available to do work that is *not* mechanical pressure-volume work.](https://en.wikipedia.org/wiki/Gibbs_free_energy#:~:text=maximum%20amount%20of%20work,%20other%20than%20pressure-volume%20work){:target="_blank"}


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111241244172667129){:target="_blank"}


