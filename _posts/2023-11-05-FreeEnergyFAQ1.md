---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'physics', math]
title: "Free energy: why it's useful"
permalink: /:year/:title:output_ext

---

In the [prior post on free energy](https://freeenergy.blog/2023/FreeEnergy2.html){:target="_blank"}, we discussed the role of the Reservoir as the "central banker" of the "energy economy" for a thermodynamic system. In other words, the Reservoir plays a *regulatory* role in the system. I've found this *control theory* perspective on a thermodynamic system to be really helpful for my intuition.

Let's further develop this intuition by diving into a FAQ on a few simple but subtle questions related to why free energy is a valuable tool for us. I also added a bonus question related to free energy for simulating molecules. 

I was confused by these questions for a long time, so I'd like to share this, and hope it is useful for others.

FAQ
--

#### Why is free energy useful for analyzing the world?

Free energy is a state variable, so it is well defined in any equilibrium state, irrespective of whether we arrived at that state via a reversible versus an irreversible process. More specifically, the *change* in free energy between two equilibrium states only depends on those starting and ending states, and does not depend on how we moved between those states. So using free energy we can consider two states, $$A$$ and $$B$$, and calculate whether state $$A$$ is going to *spontaneously* (i.e., *irreversibly*) evolve to state $$B$$, or vice versa.

#### Why does free energy always decrease in the world?  Why does a decrease in free energy predict the direction of spontaneous reactions?

For any specific thermodynamic System, with a variety of intensive/extensive variables that relate to thermal energy, mechanical energy, electrical energy, electrochemical energy, etc., we can write an expression for the change in internal energy $$U$$ that reflects those elements:

$$
dU=TdS - PdV + \sum_i Y_i dX_i
$$


The change in $$U$$ is composed of the first term $$TdS$$, which represents the interaction with the Reservoir to hold the temperature $$T$$ constant, plus additional intensive/extensive pairs with the form $$YdX$$, where $$Y$$ is an intensive variable and $$dX$$ is the change in an extensive variable (mnemonic: "X is eXtensive"). (Pressure/volume is also an intensive/extensive pair, but due to our sign conventions, the pressure-volume term has a negative sign, written as $$-PdV$$.) To perform its regulatory function, the Reservoir may also couple to the System via additional intensive/extensive pairs. And finally, the remaining intensive/extensive pairs can be considered as "energy stores" that are independent of the Reservoir. Think of them as analogous to grain silos (i.e., warehouses where commodities are stored) that the "central bank" Reservoir is not regulating. 

We can track the total energy held by the "energy stores" using the appropriate type of free energy. This free energy would *exclude* the intensive/extensive pairs used by the Reservoir for regulatory purposes, and *include* the remaining intensive/extensive pairs used for the "energy stores". For example, if the Reservoir is regulating the System's temperature and pressure, then the remaining intensive/extensive pairs (the pairs that do not relate to temperature/entropy or pressure/volume) are part of the "energy stores", and the appropriate free energy is the Gibbs free energy:

$$
dG = \sum_i Y_i dX_i
$$

When such a System undergoes a *reversible* process, the various intensive and extensive variables may change, but the total energy inside the "energy stores" will remain constant and the Gibbs free energy will remain the same. So it's analogous to grain moving between different silos, but the total amount remaining the same.

When this System undergoes an *irreversible* or *spontaneous* process, some of the energy from the "energy stores" is irreversibly converted to random thermal energy due to dissipation, which means that the Gibbs free energy will decrease, while the total entropy (the sum of the Reservoir's entropy and the System's entropy) will increase as dictated by the Second Law. So it's analogous to some of the grain becoming spoiled, so that we need to move that spoiled grain out of the grain silos and into a trash heap.

To summarize: free energy could remain the same if the System undergoes a reversible process; in all other cases, the System undergoes an irreversible and spontaneous process in which the Gibbs free energy decreases. The Gibbs free energy cannot remain constant or increase during the irreversible process because the Second Law dictates that the total entropy must increase, which forces the Gibbs free energy to decrease.


#### We sometimes see the change in Gibbs free energy given as $$ dG = \sum_i \mu_i dn_i$$, where $$\mu_i$$ and $$n_i$$ are the chemical potential and quantity of the $$i^\rm{th}$$ chemical component. Does this mean that Gibbs free energy is only used when there is a chemical reaction? Why is Gibbs free energy used in non-chemical-reaction cases such as the prediction of [protein folding](https://en.wikipedia.org/wiki/Protein_folding#:~:text=Protein%20folding%20must%20be%20thermodynamically,related%20to%20enthalpy%20and%20entropy.){:target="_blank"}, where the protein's 3D shape is changing, but the protein's chemical composition remains the same?

When we first learn thermodynamics and consider simple, idealized systems such as a gas in a box, we calculate its entropy $$S$$ as a function of internal energy $$U$$, so that if it's in equilibrium with a Reservoir at temperature $$T$$, energy will distribute between the System and the Reservoir so that total entropy is maximized, and this gives us an expected value for $$U$$. If the System consists of a single gas molecule, then the instantaneous value of $$U$$ will randomly fluctuate around the average value; typically however, we are considering a System with a very large number of molecules, and therefore the relative size of random fluctuations will be very small compared to the average value, so that we can in practice ignore the fluctuations. And for such a System with a large number of molecules, the chemical potential gives the change in free energy when the number of molecules is changed. 

When we want to model the behavior of molecules (for example, for computational drug discovery), however, we are flipping this on its head. Instead of a single System that contains many molecules, we consider an ensemble of molecules, and think of each molecule as a mini-"system" whose distribution in phase space is given by the Boltzmann distribution. For this setting, we may be less interested in the chemical potential from adding more molecules, and instead may be interested in the 3D conformation of molecules or the binding affinity between molecules. Therefore, we typically want to estimate the free energy as a function of the relevant parameters of the problem, such as the coordinates of the nuclei, the characteristics of the solvent (for example, water), etc.


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111361149185984597){:target="_blank"}
