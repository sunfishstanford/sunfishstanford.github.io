---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', 'physics', math]
title: "Confusion about thermodynamics partial derivatives"
permalink: /:year/:title:output_ext

---

In thermodynamics, we have *extensive* and *intensive* state variables. Extensive variables, such as $$n$$, the number of moles of a substance, or $$V$$, the volume of a system, scale with the size of the system. Intensive variables, such as $$T$$, the temperature, or $$P$$, the pressure, describe conditions inside the system that are invariant as you zoom into smaller parts of the system (assuming a homogeneous system at thermal equilibrium).

This seems very intuitive and straightforward. But there is actually a subtlety here that really confused me for a while. I think I've figured out a simple explanation and would like to memorialize that in this post.

Variables vs. constants 
---------

Many thermodynamics relationships involve a mix of intensive and extensive variables, such as:

$$
Y = K X^{\alpha}
$$

where $$Y$$ is intensive and $$X$$ is extensive, $$\alpha$$ is an exponent that reflects the underlying physics, and $$K$$ is a constant. But of course, $$K$$ is never really a *constant* in the sense of a physical constant such as Avogadro's number or a mathematical constant such as $$\pi$$. Instead, $$K$$ is dependent on other state variables, subject to the assumption that $$K$$ is independent of $$X$$, so that if we hold constant all state variables other than $$X$$, then $$K$$ would remain constant.

This subtlety becomes very important when we compute the various partial derivatives in thermodynamics. For example, let's consider a system that is fully specified by the extensive state variables $$(S,V,n)$$ (entropy, volume, and number of moles), and let $$Y$$ be some intensive state variable that has the following relationship with $$V$$:

$$
Y = KV
$$

$$K$$ is assumed to be independent of $$V$$, which means that we can rewrite this as

$$
Y = K(S,n)V
$$

We often specify some reference state, such as $$(S,V,n) = (S_0, V_0, n_0)$$, and we denote the value of $$Y$$ in this reference state as $$Y_0 = Y(S_0, V_0, n_0)$$. Then, we have

$$
Y = Y_0 \frac{V}{V_0}
$$

because this means that when $$V=V_0$$, then $$Y=Y_0$$ as desired. Therefore,

$$
K = \frac{Y_0}{V_0}
$$

When a "constant" is not really constant
--------------

Now, suppose we need to calculate a partial derivative such as $$\left(\frac{\partial Y}{\partial n}\right)_{S,V}$$. From the expression for $$Y$$ above, we would probably conclude that

$$
\begin{aligned}
\left(\frac{\partial Y}{\partial n}\right)_{S,V} &\stackrel{?}{=} \frac{Y_0}{V_0}\left(\frac{\partial V}{\partial n}\right)_{S,V}\\
&\stackrel{?}{=}0
\end{aligned}
$$

where the second equality is because V is held constant in the partial derivative. But we would probably be *wrong*!

We get a sense for why it's wrong by realizing that if $$Y_0/V_0$$ were constant, then $$Y$$ would not be invariant when all the extensive variables are scaled by a factor. So, recalling that $$K$$ is a function of $$S$$ and/or $$n$$, we see that $$K$$ must include the appropriate powers of $$S$$ and/or $$n$$ so that $$KV$$ remains invariant as all the extensive variables $$(S,V,n)$$ are scaled by a factor. And if $$K$$ is dependent on $$n$$, then $$\left(\frac{\partial Y}{\partial n}\right)_{S,V}$$ will be nonzero.

Example: monatomic ideal gas
-------------

Let's consider a monatomic ideal gas. The energy is

$$
U = \frac{3}{2}nRT \tag{1}\label{eq:U}
$$

and $$T$$ can be expressed in terms of the extensive variables $$(S,V,n)$$ as

$$
T = K(n) V^{-2/3} \exp(2S/3nR)
$$

We won't go through the detailed derivation of this expression for $$T$$, but basically it can be derived by using Eq. $$\eqref{eq:U}$$ and integrating 

$$
T = \left(\frac{\partial U}{\partial S}\right)_{V,n}
$$

and then using that and integrating

$$
P = -\left(\frac{\partial U}{\partial V}\right)_{S,n}
$$

Looking at the expression for $$T$$, we see that $$V^{-2/3}$$ needs to be balanced by $$n^{2/3}$$ in order for $$T$$ to be invariant under scaling of the extensive variables. Therefore, we can rewrite this as

$$
T = C \left(\frac{n}{V}\right)^{2/3} \exp(2S/3nR)
$$

where $$C$$ is a constant (this time, it *really is* a constant). 

However, we sometimes see expressions for T such as

$$
T = T_0 \left(\frac{V_0}{V}\right)^{2/3} \exp[2(S-S_0)/3nR] \tag{2?}\label{eq:TBad}
$$

where $$S_0, V_0,$$ and $$T_0$$ are the entropy, volume, and temperature of the reference state $$(S_0,V_0,n_0)$$. The constants in Eq. $$\eqref{eq:TBad}$$ were chosen so that the expression, by construction, evaluates to $$T_0$$ in the reference state.  However, using the same scaling argument for extensive variables as before, we see that Eq. $$\eqref{eq:TBad}$$ is *wrong*!!! Instead, a correct version that achieves the same manifest correspondence to the reference state values is

$$
T = T_0 \left(\frac{n V_0/n_0}{V}\right)^{2/3} \exp[2(S-n S_0/n_0)/3nR] \tag{3}\label{eq:T}
$$

To validate this, we can plug in the two candidate expressions for $$T$$, Eqs. $$\eqref{eq:TBad}$$ and $$\eqref{eq:T}$$, into the expression for internal energy $$U$$ in Eq. $$\eqref{eq:U}$$, and use the partial derivative relationships for $$T, P,$$ and $$\mu$$ to check that the expression $$TS-PV+\mu n$$ gives us back the same expression for $$U$$. The notebook below shows the results.

```python
from sympy import *
from numpy import random
# monatomic ideal gas, Morse, p. 66
# S, V, n are the independent variables; U, T, P, mu are the dependent variables
U,T,S,V,P,n,mu,S0,V0,T0, n0, R = symbols ('U,T,S,V,P,n,mu,S0,V0,T0,n0,R')

def CheckCorrectEnergy(U):
    T = diff(U,S)
    P = -diff(U,V)
    mu = simplify(diff(U,n))
    return (simplify(S*T - P*V + n*mu)) # should give back the same expression for U

UfromEq2 = 3/2 * n * R * T0 * ((V0)/V)**(2/3) * E**(2*(S-S0)/(3*n*R)) # incorrect!
UfromEq3 = 3/2 * n * R * T0 * ((n*V0/n0)/V)**(2/3) * E**(2*(S-n*S0/n0)/(3*n*R)) # correct

display (CheckCorrectEnergy(UfromEq2)) # incorrect!
display (CheckCorrectEnergy(UfromEq3)) # correct

```


$$
T_{0} \left(\frac{V_{0}}{V}\right)^{0.666666666666667} \cdot \left(0.5 R n + 1.0 S_{0}\right) e^{\frac{2 \left(S - S_{0}\right)}{3 R n}}
$$


$$
1.5 R T_{0} n \left(\frac{V_{0} n}{V n_{0}}\right)^{0.666666666666667} e^{\frac{2 \left(S n_{0} - S_{0} n\right)}{3 R n n_{0}}}
$$




---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/110482651760587530){:target="_blank"}



