---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math, 'probability theory']
title: "The Performance Difference Lemma in Reinforcement Learning"
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

The Performance Difference Lemma provides a nice way to reinforce some of the basic concepts in policy gradients for reinforcement learning.

Proof of the lemma
--------

Assume starting state $$s_0 \sim \rho_0(s_0)$$, where $$\rho_0$$ is a distribution for the initial state.

We would like to prove the following:


$$
J(\pi_1) - J(\pi_2) 
= \mathbb{E}^{\pi_1} \left[ \sum^{\infty}_{t=0} \gamma^t A^{\pi_2}(s_t, a_t) \right]  ,
$$

where the expectation is over trajectories sampled from the policy $$\pi_1$$, and each trajectory is

$$
\tau = (s_0, a_0, s_1, a_1, \dots) .
$$

Also $$\gamma$$ is a discount factor, and $$A^{\pi_2}(s_t, a_t) \equiv Q^{\pi_2}(s_t, a_t) - V^{\pi_2}(s_t)$$ is the advantage
function for policy $$\pi_2$$.

We begin, using the definition for policy value

$$
\begin{align}
J(\pi_1) - J(\pi_2) 
&= \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ V^{\pi_1}(s_0) - V^{\pi_2}(s_0) \right] && \leftarrow \text{no } a_0 \text{ dependence} \\
\end{align}
$$

Here, specifying the expectation to also be over $$\pi_1$$ and $$a_0$$ is a no-op, as the value functions do not depend on 
the action $$a_0$$ (and hence do not depend on whether the expectation samples $$a_0$$ from the policy $$\pi_1$$).

We continue:

$$
\begin{align}
&= \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ V^{\pi_1}(s_0) - Q^{\pi_2}(s_0, a_0) \right] + \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ Q^{\pi_2}(s_0, a_0) - V^{\pi_2}(s_0) \right]  && \leftarrow \text{subtract and add } Q^{\pi_2}(s_0, a_0)  \\

&= \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ V^{\pi_1}(s_0) - Q^{\pi_2}(s_0, a_0) \right] + \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ A^{\pi_2}(s_0, a_0)  \right]    \\

&= \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ A^{\pi_2}(s_0, a_0) \right] + \mathbb{E}^{\pi_1}_{\substack{s_0, a_0 \\ s_1, a_1}} \left[ V^{\pi_1}(s_0) - Q^{\pi_2}(s_0, a_0) \right] && \leftarrow \text{no-op, since no } s_1, a_1 \text{ dependence} \\

&= \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ A^{\pi_2}(s_0, a_0) \right] + \mathbb{E}^{\pi_1}_{\substack{s_0, a_0 \\ s_1, a_1}} \left[ Q^{\pi_1}(s_0, a_0) - Q^{\pi_2}(s_0, a_0) \right]   \\

\end{align}
$$

In the last line, the state value function $$V$$ at a state is the same as the state-action value function $$Q$$ at the state
and action tuple sampled along the same trajectory.


Next, we have:

$$
\begin{align}
&= \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ A^{\pi_2}(s_0, a_0) \right] + \mathbb{E}^{\pi_1}_{\substack{s_{0:1} \\ a_{0:1}}} \left[ \left( R(s_0, a_0) + \gamma V^{\pi_1}(s_1) \right) - \left( R(s_0, a_0) + \gamma V^{\pi_2}(s_1) \right) \right] 
\end{align}
$$

The last line follows from the definition of a $$Q$$ function. Note that since $$(s_0,a_0)$$ is given by the trajectory, the next
state $$s_1$$ necessarily follows from the dynamics of the environment (independent of the policy). Therefore, the only
difference between $$Q^{\pi_1}$$ and $$Q^{\pi_2}$$ is how each uses its own policy's value function to evaluate the state $$s_1$$.

Continuing:


$$
\begin{align}
&= \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ A^{\pi_2}(s_0, a_0) \right] + \mathbb{E}^{\pi_1}_{\substack{s_{0:1} \\ a_{0:1}}} \left[ \gamma V^{\pi_1}(s_1) - \gamma V^{\pi_2}(s_1) \right] && \leftarrow \text{next, expand the right side the same way } \\

\\
&= \mathbb{E}^{\pi_1}_{s_0, a_0} \left[ A^{\pi_2}(s_0, a_0) \right] + \mathbb{E}^{\pi_1}_{\substack{s_{0:1} \\ a_{0:1}}} \left[ \gamma A^{\pi_2}(s_1, a_1) \right] + \cdots \\
\end{align}
$$

And we finally have:

$$
\begin{align}
\boxed{ J(\pi_1) - J(\pi_2) 
=  \mathbb{E}^{\pi_1} \left[ \sum_{t=0}^{\infty} \gamma^t A^{\pi_2}(s_t, a_t) \right]}  && \text{QED}
\end{align}
$$




---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/115839688418406455){:target="_blank"}
[Share or comment on Bluesky](https://bsky.app/profile/sunfishstanford.bsky.social/post/3mbn773vlyk2n){:target="_blank"}


[//]: #  https://gist.github.com/pierrejoubert73/902cc94d79424356a8d20be2b382e1ab
