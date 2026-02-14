---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'physics', math]
title: "Free Energy FAQ Part 2"
permalink: /:year/:title:output_ext

---
Need to write up the rest of these ideas...

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


