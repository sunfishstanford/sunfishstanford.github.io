---
layout: post
usemathjax: true
categories: [math, physics, 'embracing transitory confusion']
title: "Confusion about imperfect differentials and state variables in thermodynamics"
permalink: /:year/:title:output_ext

---

When you learn thermodynamics, one of the first new concepts encountered is that there are state variables (e.g., energy), which are properties uniquely determined by the "current state of the system" and not dependent on the prior history (all this is assuming thermal equilibrium); this is to be contrasted with other properties that depend on prior history and therefore are NOT state variables (e.g., work or heat). And then we learn about *perfect* differentials (corresponding to state variables) versus *imperfect* differentials (corresponding to properties that are *not* state variables).

When I first learned this in introductory thermodynamics, this confused the heck out of me and felt very unsatisfactory. I could see that the work and/or heat between two points in state space depends on the path taken (i.e., depends on the prior history), but is there a deeper reason why work and heat have imperfect differentials? What is the underlying mathematical logic?

And then there were similar sounding concepts from Electricity & Magnetism such as conservative fields (e.g., electrostatic fields from charge distributions) that are related to gradients of potentials, and path integrals of conservative fields that are insensitive to the specific path taken between fixed starting and ending points. Is this another aspect of the same thing?

The answer, of course, is YES! And I think there is a simple way to explain this.

State, history, and state variables
-------------

First, let's talk about state, history, and state variables. We assume that there is a physical system where a number of macroscopic properties (typically for a simple gas, this could be temperature, pressure, volume, and number of molecules) that have fixed functional relationships with each other (this functional relationship is called the *equation of state*). This means that if there are $$n$$ properties, then if we specify all but one of these properties, then the last remaining property will be uniquely determined via the equation of state. For example, you could have the ideal gas law, $$PV=N k_B T$$. Since there are many ways by which you could arrive at a given set of values for these properties (for example, you could arbitrarily pick two properties, and vary those two properties with the constraint that you continue to satisfy the equation of state while keeping all other properties fixed), this implies that you are not sensitive to the history of how you arrived at the current situation (you are not sensitive to the path taken in state space). We think of the path taken as the "history", because we think of varying the system by following the "path" as time advances.

So this is what is meant by thermal equilibrium–that the system has "forgotten" its prior history (or you could say that the system "doesn't care" what its prior history was). And in thermal equilibrium, the $$n$$ properties are called state variables, and the *state space* is the $$n-1$$-dimensional surface in a $$n$$-dimensional manifold of these state variables ($$n-1$$, because there is one constraint from the equation of state), where each point in the state space is a unique state that is valid according to the equation of state.

Of course, we could have defined a "meta-state" by specifying a starting point in state space, an ending point in state space, and the specific path taken that connects the starting point to the ending point. Such a meta-state by definition is dependent on the history, but this is not what we do for equilibrium thermodynamics because it turns out we can get a vast amount of interesting results by ignoring the history. So coming back to energy, work, and heat, we recognize that energy is uniquely defined for each point in state space, but work and heat are not uniquely defined. 

Btw, we could also have included energy as one of the state variables that comprise the dimensions of state space, in which case it is explicitly uniquely defined for each point. And we see that calling a property a state variable is different from saying that the property is one of the dimensions that comprise a state space. But this is probably very obvious–we could of course define an arbitrary new property that is a function of state variables, in which case this new property is a state variable because it is uniquely defined at each point in state space, yet the state space does not include this new value as one of its dimensions. In other words, there is a specific number of dimensions for the state space (this is determined by the physics of the situation), whereas there are an *unlimited* number of properties that could be state variables.

So if we had used the meta-state definition to define our state space, then work and heat would be uniquely defined for each meta-state. But in our simple, thermal equilibrium state space, work and heat are *NOT* uniquely defined on the state space, and therefore they are not state variables.

Perfect versus imperfect differentials
-----------

Now, for a state variable such as energy, since it is defined on state space (which is a differentiable manifold), we can calculate its gradient to see how energy changes as we move to different points in state space. This gradient is our desired differential for energy. And the fundamental theorem of calculus tells us that we can integrate the differential to get back to the change in energy between two points, independent of the connecting path. So this is called a perfect differential, and it is why a state variable is associated with a perfect differential. From thermodynamics, we learned that all perfect differentials must satisfy a simple rule, which is that if you pick any of the components of a perfect differential and take the partial derivatives of that component with respect to all other dimensions, you must get the same result independent of which component you happened to pick initially. Now that we understand that a perfect differential is the gradient of a state variable, we see that this rule is just the statement that the order of taking partial derivatives does not matter.

For something like work, which is not a state variable, it doesn't make sense to take its gradient across state space because work is not a function defined on state space. However, we can think about what happens if we start at a given state and move a small step to an adjacent state. Then, we get the imperfect differential for work: $$\delta W = P dV$$. This means that if we take a small step in state space so that the change in volume is $$dV$$ (together with other possible changes in state variables), then the additional work will only depend on $$P$$ multiplied by the step $$dV.$$ So to calculate what the total change in work is along some path that is specified, we proceed along that path using small steps and apply this rule. The resultant total work will clearly be dependent on the precise path taken in state space, which goes back to the fact that work is not uniquely defined in state space.

And finally, the situation in E&M is exactly analogous if we replace energy with potential, the state space dimensions with cartesian spatial dimensions, and the perfect differential with the electric field. And so a conservative field is simply the gradient of a scalar function that is well defined in space.


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/109922026796201683){:target="_blank"}
