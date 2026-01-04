---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math]
title: "Policy Gradient Latex Notation"
permalink: /:year/:title:output_ext

---
<style>
  .dropdown-container {
    display: inline; /* Ensures it stays inline with other text */
    cursor: pointer;
  }
  .dropdown-arrow {
    margin-left: 5px; /* Add some space between text and arrow */
    transform: rotate(0deg); /* Initial state */
    transition: transform 0.2s ease; /* Smooth rotation */
    display: inline-block;
  }
  .dropdown-content {
    display: none; /* Hidden by default */
  }
  .dropdown-container.active .dropdown-arrow {
    transform: rotate(90deg); /* Rotate arrow when active */
  }
  .dropdown-container.active .dropdown-content {
    display: inline; /* Show content when active */
  }
</style>

<script>
  function toggleDropdown(element) {
    element.classList.toggle('active');
  }
</script>

$$\newcommand\dag\dagger$$


The following (generated via ChatGPT) is helpful for following derivations related to policy gradient and similar topics.

# Summing / Expectation Over Trajectories in Policy Gradient Methods

This document shows **standard, authoritative LaTeX notation** for summing over (or taking expectations over) trajectories sampled from a policy in reinforcement learning.

---

## 1. Trajectory definition

A trajectory is typically denoted by:


$$
\tau = (s_0, a_0, s_1, a_1, \dots, s_T)
$$

---

## 2. Trajectory distribution induced by a policy

The probability of a trajectory under policy $$ \pi_\theta $$ is:

$$
p_\theta(\tau)
=
\rho_0(s_0)
\prod_{t=0}^{T}
\pi_\theta(a_t \mid s_t)\, P(s_{t+1} \mid s_t, a_t)
$$

---

## 3. Expectation over trajectories (canonical form)

The **most standard and widely accepted notation** is:

$$
\mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ f(\tau) \right]
$$

Equivalent summation form (discrete case):

$$
\sum_{\tau} p_\theta(\tau)\, f(\tau)
$$

---

## 4. Policy gradient theorem (trajectory form)

$$
\nabla_\theta J(\theta)
=
\mathbb{E}_{\tau \sim p_\theta(\tau)}
\left[
\sum_{t=0}^{T}
\nabla_\theta \log \pi_\theta(a_t \mid s_t)\, G_t
\right]
$$

---

## 5. Likelihood-ratio form

$$
\nabla_\theta J(\theta)
=
\sum_{\tau}
p_\theta(\tau)\,
\nabla_\theta \log p_\theta(\tau)\,
R(\tau)
$$

with

$$
\nabla_\theta \log p_\theta(\tau)
=
\sum_{t=0}^{T}
\nabla_\theta \log \pi_\theta(a_t \mid s_t)
$$

---

## 6. Discounted state-visitation (time-marginalized) form

$$
\nabla_\theta J(\theta)
=
\sum_{s}
d^\pi(s)
\sum_{a}
\pi_\theta(a \mid s)
\nabla_\theta \log \pi_\theta(a \mid s)\,
Q^\pi(s,a)
$$

---

## 7. Monte Carlo estimator (empirical average)

$$
\nabla_\theta J(\theta)
\approx
\frac{1}{N}
\sum_{i=1}^{N}
\sum_{t=0}^{T}
\nabla_\theta \log \pi_\theta(a_t^{(i)} \mid s_t^{(i)})
\, G_t^{(i)}
$$

---

## 8. Authoritative sources for this notation

1. **Sutton & Barto (2018)**
   *Reinforcement Learning: An Introduction (2nd ed.)*
   – Chapters 13–14 (Policy Gradient Methods)

2. **Williams (1992)**
   *Simple Statistical Gradient-Following Algorithms for Connectionist Reinforcement Learning*
   – Introduces REINFORCE and trajectory expectations

3. **Schulman et al. (2015)**
   *Trust Region Policy Optimization*
   – Uses explicit \( \tau \sim p_\theta(\tau) \) notation

4. **Silver et al. (2014)**
   *Deterministic Policy Gradient Algorithms*

5. **Levine (2018)**
   *Lecture Notes on Reinforcement Learning* (UC Berkeley)

These sources consistently use expectations or sums over
$$ \tau \sim p_\theta(\tau) $$ as the canonical way to denote
sampling trajectories from a policy.

---

## 9. Key takeaway

$$
\boxed{
\mathbb{E}_{\tau \sim p_\theta(\tau)}[\cdot]
\;\;\equiv\;\;
\sum_{\tau} p_\theta(\tau)(\cdot)
}
$$

This is the **standard, authoritative mathematical notation** for summing over trajectories sampled from a policy.





---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/113631240589287684){:target="_blank"}


[//]: #  https://gist.github.com/pierrejoubert73/902cc94d79424356a8d20be2b382e1ab
