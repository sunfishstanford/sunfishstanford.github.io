---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'physics', math]
title: "Free Energy, Part I"
permalink: /:year/:title:output_ext

---

This blog is called *Free Energy*, so let's talk about free energy!

When I first learned thermodynamics, free energy for me was a mysterious and confusing concept. There were so many questions, such as:

- What does "free" mean? The standard choices are "free" as in "free beer" or "free" as in "free speech". Here, it's clear that it couldn't be the first choice, but in what sense is free energy "free" as in "freedom"?
- What explains the different properties of Gibbs free energy versus Helmholtz free energy? Why is there a distinction around "non-PV work" or "non-mechanical work"?
- Why does free energy always decrease in the world?  Why does that predict the direction of spontaneous reactions?
- We sometimes see Gibbs free energy defined as [$$ \sum_i \mu_i n_i$$](https://en.wikipedia.org/wiki/Gibbs_free_energy#:~:text=This%20result%20shows%20that%20the%20chemical potential%20of%20a%20substance){:target="_blank"}, where $$\mu_i$$ is the chemical potential of the $$i^\rm{th}$$ component. Does this mean that Gibbs free energy is only used when there is a chemical reaction where substances transform chemically among its components? Why is Gibbs free energy used in non-chemical-reaction cases such as the prediction of [protein folding](https://en.wikipedia.org/wiki/Protein_folding#:~:text=Protein%20folding%20must%20be%20thermodynamically,related%20to%20enthalpy%20and%20entropy.){:target="_blank"}?

In Part I of this post, let's dive into the meaning of "free".

"Free" as in "freedom"
--------

As a simple example, consider a homogeneous substance such as a gas (we call that the "System") that is in thermal equilibrium with a large thermal reservoir (the "Reservoir") at temperature $$T$$. The [internal energy of the System](https://en.wikipedia.org/wiki/Internal_energy#:~:text=integrated%20and%20yields%20an%20expression%20for%20the%20internal%20energy){:target="_blank"} is

$$
U = T S - P V + \mu n,
$$

where $$S$$ is entropy, $$P$$ is pressure, $$V$$ is volume, $$\mu$$ is chemical potential, and $$n$$ is the number of moles of the gas.

By compressing the gas and reducing $$V$$ to increase $$P$$, an external force can perform work and store energy in the System. If this is done slowly enough to ensure the process is reversible, then the same quantity of stored energy can be released back to the outside by reversing the process. So the System acts like a "battery" that can be charged or discharged, and we would like to calculate the amount of stored energy that can be "charged" or "discharged" when the System moves to a new state.

Seems simple, right? This seems similar to compressing a spring and storing energy in the potential energy of the spring, except here we are storing energy in the compression of the gas. So since we have an expression for the internal energy $$U$$, could we just calculate the change in $$U$$ as the system moves between two different states, to get the the amount of stored energy?

Unfortunately, this System is not as simple as a spring that stores energy. The difference here is that because the System is at thermal equilibrium with the Reservoir, energy can flow freely between the System and the Reservoir to maximize entropy. Therefore, as the external force does work on the System, that stored energy is mixed with the energy that flows between the System and the Reservoir, and we need to disentangle the two. 

We can do that by considering the [differential change of the internal energy](https://en.wikipedia.org/wiki/Internal_energy#:~:text=The%20differential%20internal%20energy%20may%20be%20written){:target="_blank"},

$$
dU = T dS - P dV + \mu dn.
$$

The $$TdS$$ term is the energy that flows between the System and the Reservoir to maintain thermal equilibrium to keep the temperature fixed at $$T$$. The $$-PdV$$ term is the change in the stored energy, so we would like to isolate this term so that we can integrate to get the total stored energy. And if the number of moles of the gas is constant, then $$dn=0$$, and we can eliminate the $$\mu dn$$ term. 

To eliminate the $$TdS$$ term, we define a new quantity $$F$$, the *Helmholtz free energy*,

$$
F = U - TS.
$$

Since $$U$$, $$T$$, and $$S$$ are all state variables, $$F$$ is also a state variable. The differential change in $$F$$ is

$$
dF = dU - TdS - SdT.
$$

So at constant $$T$$, $$dT=0$$, and we have

$$
dF = dU - TdS.
$$

Using the expression for $$dU$$ above and recalling that $$dn=0$$, we finally get

$$
dF = -PdV,
$$

isolating the change in stored energy as desired. 

In the special case of an ideas monatomic gas, the behavior of the system is very simple. The internal energy of the gas is $$U = (3/2) nRT$$. Therefore, at constant $$T$$, the internal energy $$U$$ remains constant. So all the energy from the work that is put into the gas by compressing the gas--all that energy flows into the Reservoir. In the case of an ideal monatomic gas, the Reservoir is actually storing all the energy!

For an arbitrary type of gas or other substance in general, we could imagine that the energy is stored in two steps. In Step 1, the gas is isolated from the reservoir, work is done to compress the gas, its energy increases, and its temperature increases. At this point, the gas temperature is higher than the Reservoir temperature, but its entropy has not changed (because the work has been done in a reversible manner and no heat could flow out of the gas). Then in Step 2, a Carnot engine is used to extract work by pumping heat from the gas to the Reservoir, thereby gradually lowering the temperature of the gas until it reaches the Reservoir's temperature of $$T$$. Because heat will have flowed out of the gas during this step, the entropy of the gas will decrease. And the work done by the Carnot engine is performed on the external system, to partially offset the work done in Step 1, but the external system's net work done on the gas will still be positive (because if that were not true, we would then have a perpetual motion machine that violates the Second Law). By breaking this down into these two steps, we see that the $$-PdV$$ term represents the energy coming into the gas from the work done on it, but it is partially or completely offset by the $$TdS$$ term representing the reduction in entropy of the gas, so at least a part of the stored energy is in the Reservoir.

So to answer the original question: we call $$F$$ the "free energy" because it is the stored energy that is available to do useful work on external systems. *It is "free" as in "freedom" in the sense that it is the portion of the energy that is not "bound"*; it can be extracted from the System+Reservoir by having the System do work on an external object. [^1]

[^1]: The rest of the internal energy $$U$$ (recall that $$U$$ is greater than $$F$$ by the quantity $$TS)$$ is not "free" because it can only be extracted if there is another thermal reservoir at a temperature $$T_2$$ that is lower than $$T$$, in which case we could run a heat engine between these two temperatures to produce useful work.


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111067078789655621){:target="_blank"}


