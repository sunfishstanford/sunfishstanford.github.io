---
layout: post
usemathjax: true
categories: [math, physics, 'embracing transitory confusion']
title: "Confusion about imperfect differentials and state variables in thermodynamics"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

When you learn thermodynamics, one of the first new concepts encountered is that there are state variables (e.g., energy) that are properties uniquely determined by the state and not dependent on the prior history (all this is assuming equilibrium states), versus properties that depend on prior history and therefore are NOT state variables (e.g., work or heat). And then we learn about *perfect* differentials (corresponding to state variables) versus *imperfect* differentials (corresponding to properties that are *not* state variables).

When I first learned this in college, at the time I thought I was pretty good at calculus, yet this confused the heck out of me and felt very unsatisfactory. I could see that the work and/or heat between two points in state space depends on the path taken, but is there a deeper reason why work and heat have imperfect differentials? What is the underlying mathematical logic?

And then there were similar sounding concepts from E&M physics such as conservative fields (e.g., electrostatic fields from charge distributions) that are related to gradients of potentials, and the fact that the path integrals of conservative fields depend only on starting and ending points. Is this another aspect of the same thing?

The answer, of course, is YES! And I think there is a simple way to explain this.

State, history, and state variables
-------------

First, let's talk about state, history, and state variables. We assume that there is a physical system where a number of macroscopic properties (typically for a simple gas, this could be temperature, pressure, volume, and number of molecules) that have fixed functional relationships with each other. This means that if there are $$n$$ properties, then if we specify all but one of these properties, then the last remaining property will be uniquely determined. For example, you could have the ideal gas law, $$PV=N k_B T$$. Since there are many ways by which you could arrive at a given set of values for these properties (for example, you could vary two properties with the constraint that you continue to satisfy the functional relationships, while keeping all other properties fixed), this implies that you are not sensitive to the history of how you arrived at the current situation. This is what is meant by thermal equilibrium–that the system has "forgotten" its prior history. And in thermal equilibrium, the $$n$$ properties are called state variables, and the *state space* is the $$n$$-dimensional space of these state variables, where each point in the state space is a unique state.

Of course, we could have defined a "meta-state" by specifying a starting point in state space, an ending point in state space, and the specific path taken that connects the starting point to the ending point. Such a meta-state by definition is dependent on the history, but this is not what we do for equilibrium thermodynamics because it turns out we can get a vast amount of interesting results by ignoring the history. So coming back to energy, work, and heat, we recognize that energy is uniquely defined for each point in state space, but work and heat are not uniquely defined. 

Btw, we could also have included energy as one of the state variables that comprise the dimensions of state space, in which case it is explicitly uniquely defined for each point. And we see that calling a property a state variable is different from saying that the property is one of the dimensions that comprise a state space. But this is probably very obvious–we could clearly define an arbitrary new function of state variables, so that this new value is a state variable because it is uniquely defined at each point in state space, yet the state space does not include this new value as one of its dimensions.

So if we had used the meta-state definition to define our state space, then work and heat would be uniquely defined for each meta-state. But in our simple, equilibrium state space, work and heat are *NOT* uniquely defined on the state space, and therefore they are not state variables.

Perfect versus imperfect differentials
-----------

Now, for a state variable such as energy, since it is defined on state space (which is a differentiable manifold), we can calculate its gradient to see how energy changes as we move to different points in state space. This gradient is our desired differential for energy. And the fundamental theorem of calculus tells us that we can integrate the differential to get back to the change in energy between two points, independent of the connecting path. So this is called a perfect differential, and it is why a state variable is associated with a perfect differential. And we get the simple rule that all perfect differentials must satisfy (namely, that when you take the partial derivatives of each component of a differential wrt all other dimensions, you must get the same result), based on the fact that the order of taking partial derivatives does not matter.

For something like work, which is not a state variable, it doesn't make sense to take its gradient across state space because work is not a function of state space. However, we can think about what happens if we start at a given state and move a small step to an adjacent state. Then, we get the imperfect differential for work: $$dW = P dV$$. (The differential symbol is supposed to have a slash in it to denote an imperfect differential, but I don't know how to typeset that.) This means that if we take a small step in state space so that the change in volume is $$dV$$ (together with other possible changes in state variables), then the additional work will only depend on $$P$$ multiplied by the step $$dV$$. So this is the recipe: to calculate what the total change in work is, we follow a path in state space and apply this rule. This is great, except we now are dependent on the precise path taken in state space, which goes back to the fact that work is not uniquely defined in state space.

And finally, the situation in E&M is exactly analogous if we replace energy with potential, the state space dimensions with cartesian spatial dimensions, and the differential with the electric field. And so a conservative field is simply the gradient of a scalar function that is well defined in space.


---

[Comment on Mastodon](https://hachyderm.io/@Sunfishstanford/109624369727398121){:target="_blank"}
