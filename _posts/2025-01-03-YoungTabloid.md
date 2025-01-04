---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math]
title: "A combinatorial lemma on Young tabloids"
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

In the [lecture notes by G.D. James on the representation theory for symmetric groups](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://www-users.cse.umn.edu/~webb/oldteaching/Year2010-11/the-representation-theory-of-the-symmetric-groups-SLN.pdf&ved=2ahUKEwjW69DIuduKAxWmHkQIHZTFAiUQFnoECBkQAQ&usg=AOvVaw2TD7GrvL8QvfLtmjFT3Ck_){:target="_blank"},
the proof for Lemma 4.6 has this line: "Also, if $$\lambda=\mu$$, then $$\{t^*\}$$ is one of the tabloids involved in $$\{t\}\kappa_t$$, by construction."
This post is to remind myself how this works.

First, recall that James uses a left to right notation, where the operators act from the right side.

In the line before the quoted line above, James proved that for any row in the tableau $$t^*$$ all the numbers belong to different columns in the tableau $$t$$. 
So we would like to prove that we can construct a tableau $$t_1 \in \{t^*\}$$ where every number is in the same column as in $$t$$. 
That would mean that $$t_1 = t c$$, where $$c \in C_t$$, the column stabilizer of $$t.$$
And that would mean that $$\{t^*\} = \{t_1\} = \{t c\} = \{t\}c.$$
And since $$c$$ is one of the permutations in $$\kappa_t,$$ the signed column sum, that means that $$\{t^*\}$$ is one of the tabloids involved in $$\{t\}\kappa_t$$.

We can freely apply permutations from the row stabilizer of $$t^*$$ to construct tableaus that are in $$\{t^*\}.$$
So we start with the top set of rows of $$t^*$$ with the maximum number of columns. 
In each row, we permute the numbers so that they are moved to the columns that correspond to their columns in $$t$$.
This is possible due to the pigeonhole principle, because each number in a given row in $$t^*$$ corresponds to a different column in $$t,$$ and the maximum number of columns available in $$t$$ are the same as the maximum number of columns available in $$t^*$$.

Now, compare these rows with the next lower row, which has fewer columns.
The extra column(s) in these rows now has numbers which map to the corresponding extra column(s) in $$t$$. 
Therefore, again via pigeon hole, every number in $$t$$ in those extra column(s) must now be in the extra column(s) in $$t^*$$.

Therefore, we know that in the remaining rows in $$t^*$$, no other numbers will map to those extra columns in $$t$$. So we can move on to the next set of rows with the next largest number of columns, and repeat the same process until the entire tableau has been rearranged.
And this way we can construct $$t_1$$ as desired.




---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/113631240589287684){:target="_blank"}


[//]: #  https://gist.github.com/pierrejoubert73/902cc94d79424356a8d20be2b382e1ab
