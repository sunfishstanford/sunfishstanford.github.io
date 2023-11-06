---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'physics', math]
title: "Free Energy FAQ"
permalink: /:year/:title:output_ext

---

In the [prior post on free energy](http://localhost:4000/2023/FreeEnergy2.html){:target="_blank"}, we discussed the role of the Reservoir as the "central banker" of the "energy economy" for a thermodynamic system. In other words, the Reservoir plays a *regulatory* role in the system. I've found this *control theory* perspective on a thermodynamic system to be really helpful for my intuition.

Let's further develop this intuition by diving into a FAQ on a few simple but subtle questions. I was confused by these for a long time, so I'm excited to share this, and hope it is useful for others.

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

When we first learn thermodynamics and consider simple, idealized systems such as a gas in a box, we calculate its entropy $$S$$ as a function of internal energy $$U$$, so that if it's in equilibrium with a Reservoir at temperature $$T$$, energy will distribute between the System and the Reservoir so that total entropy is maximized. This therefore gives us an expected value for $$U$$, namely the value of $$U$$ that maximizes total entropy. If the System consists of a single gas molecule, then the instantaneous value of $$U$$ will randomly fluctuate around the average value; typically however, we are considering a System with a very large number of molecules, and therefore the relative size of random fluctuations will be very small compared to the average value, so that we can in practice ignore the fluctuations. And for such a System with a large number of molecules, the chemical potential gives the change in free energy when the number of molecules is changed. 

When we want to model the behavior of molecules (for example, for computational drug discovery), however, we are flipping this example on its head. Instead of a single System that contains many molecules, we consider an ensemble of molecules, and think of each molecule as a mini-"system" whose distribution in phase space is given by the Boltzmann distribution. For this setting, we may be less interested in the chemical potential from adding more molecules, and instead may be interested in the 3D conformation of molecules or the binding affinity between molecules. Therefore, we typically want to estimate the free energy as a function of the relevant parameters of the problem, such as the coordinates of the nuclei, the characteristics of the solvent (for example, water), etc.


#### For molecular conformation calculations, we use Gibbs free energy because the systems are at constant T and P. But dG=0 if dn=0, and for molecular conformation changes, dn=0. So why is Gibbs free energy useful?

"Bonus round" questions
----

#### Since energy is conserved in the universe, the total energy does not change as a system moves from turbulence (non-equilibrium) to equilibrium. How is entropy defined during that process? Why isn’t it a single number that is determined by the total energy, in which case entropy should remain constant? And if we have a nonequilibrium state followed by settling into an equilibrium state, then non-equilibrium again, etc., don’t we have the same total energy at all times? Why are there multiple equilibrium states with successively greater entropy for the same total energy in the universe?

reversible vs irreversible: relates to whether entropy is constant vs increasing; this means that reversible can run backwards, but irreversible is one-direction-only

equilibrium vs non-equilibrium: relates to whether you wait for things to settle to the point where the state variables remain constant and the system loses memory of its past (meaning that multiple non-equilibrium starting points can lead to the same equilibrium state)

reversible processes are always very near equilibrium
irreversible processes could depart far from equilibrium, but at the end of the process you can let the system settle to reach equilibrium again

* express differential equation for entropy change as dS = 1/T dU + …
* S depends on multiple state variables in addition to U
* when we say that the system can be in equilibrium and then moves via an irreversible process to a new equilibrium, what we mean is that there are certain constraints on the system and equilibrium is reached, and then some constraints are removed or changed, and then the system needs to settle into a new equilibrium
* this process of settling is an irreversible process during which global entropy increases
* Having constraints change can be modeled as partitioning the system in different subunits, such that when the constraints are configured a certain way, each subunit can be in equilibrium because in a given subunit the intensive variables are uniform
* The total entropy is then the sum of the entropies of the subunits, and the total energy is the sum also; by conservation of energy, the sum of energies must be constant
* But even though the total energy is constant, the state variables in individual subunits are changing, and therefore entropy is changing, and in fact the total entropy must monotonically increase 


#### Consider the differential equation for internal energy: dU = TdS - PdV + …  When is this valid, and when is it not valid?

dU = TdS - PdV + …, holds for both reversible and irreversible processes because U, T, S, P, V, etc. are state variables, so there is a well behaved function U(S,V,…) whose partial derivatives are T = dU/dS (at constant V, etc.), …
And in any equilibrium state, this is true, irrespective of whether we arrived at that state via a reversible or irreversible process
But this depends on state variables being well defined, which depends on the system having settled into equilibrium
So in the middle of some irreversible process, where the system is in non-equilbrium and the state variables are not well defined (eg, pressure is not uniform), this differential equation will not be valid


#### What is the meaning of having two ways to express dU?

dU = dQ - dW
dU = TdS - PdV
We view TdS as the heat energy that flows into a system to increase U, and that also increases S, so dQ = TdS
But we know that for irreversible process, dQ < TdS. How do we reconcile that with this dU equation?







---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111241244172667129){:target="_blank"}


