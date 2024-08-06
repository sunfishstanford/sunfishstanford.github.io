---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math, physics]
title: "Direct sum versus Cartesian product versus tensor product of vector spaces"
permalink: /:year/:title:output_ext

---

I regularly get confused about direct sums vs. Cartesian products vs. tensor products of vector spaces if it's been a while since I last thought about the topic, and then I would need to re-remember how things work. So I decided to jot down these notes to save some time in the future. (Note: we are only considering "sums" and "products" of finite numbers of spaces.)

Cut to the chase
------
The direct sum $$A \oplus B$$ is the Cartesian product of the vector spaces $$A$$ and $$B$$. 


The tensor product $$A \otimes B$$ is the vector space that is spanned by a basis that is the Cartesian product of bases $$B_A$$ and $$B_B$$. Here, $$B_A$$ and $$B_B$$ are the bases for $$A$$ and $$B$$, respectively.



Direct sum
------
Suppose we have two spaces $$A$$ (dimension $$d_A$$ and basis $$B_A$$) and $$B$$ (dim $$d_B$$ and basis $$B_B$$), and we form a direct sum space $$S=A \oplus B$$ (dimension $$d_S$$ and basis $$B_S$$) and a tensor product space $$P = A \otimes B$$ (dimension $$d_P$$ and basis $$B_P$$).

E.g., let $$A$$ and $$B$$ both be 3-dimensional vector spaces ($$d_A = d_B = 3$$), with $$B_A = \{a_1,a_2,a_3\}$$ and $$B_B = \{b_1,b_2,b_3\}$$.

Then the direct sum space $$S=A \oplus B$$ has basis $$B_S = B_A \cup B_B$$, i.e., $$B_S =  \{a_1, a_2, a_3, b_1, b_2, b_3 \}$$. So the dimension of $$S$$ is $$d_S = d_A + d_B = 6$$, and each element of $$S$$ is described by 6 components. In other words, the dimensions of $$A$$ and $$B$$ are added together when performing a direct sum.

What if we recursively form a second level of direct sums? For example, let $$C$$ and $$D$$ be two 2-dimensional spaces with bases $$\{c_1,c_2\}$$ and $$\{d_1,d_2\}$$, respectively, and let $$T=C \oplus D$$. Now let $$R=S \oplus T = (A \oplus B) \oplus (C \oplus D) $$. Then the basis for $$R$$ is $$B_R = \{ a_1,a_2,a_3,b_1,b_2,b_3,c_1,c_2,d_1,d_2 \}$$.

So, we see that for direct sums of a bunch of vector spaces, we just take the basis vectors of each vector space, throw them all together into a bucket, and then the direct sum space is  comprised of linear combinations of all the basis vectors in this bucket.

The direct sum of a bunch of vector spaces is also the same thing as the Cartesian product of the vector spaces. To see this, recall that a Cartesian product of two sets is constructed via an ordered pair where the first member of the ordered pair is chosen from the first set and the second member is chosen from the second set, and we iterate over all possible choices. Therefore, a nested series of Cartesian products is a nested series of ordered pairs. But such a nested series of various items is, for the current purpose, equivalent to a simple flat list of all of the items. And each item in the list is a possible choice from one of the vector space. And each choice from a vector space is actually a list of choices of possible multipliers of the basis vectors for that space. So the end result is formally a linear combination of all of the basis vector from all of the vector spaces, which is the same thing as a direct sum.

Tensor product
--------
For a tensor product space $$P = A \otimes B$$, the basis $$B_P$$ is the *Cartesian product* of the original bases. Therefore, 

$$\begin{aligned}
B_P &= B_A \times B_B \\
&= \{ (a_1,b_1), (a_1,b_2), (a_1,b_3), (a_2,b_1), (a_2,b_2),(a_2,b_3),(a_3,b_1),(a_3,b_2,),(a_3,b_3) \}.
\end{aligned}
$$ 

Thus, the tensor product space $$P$$ is comprised of linear combinations of these basis vectors. So we see that the dimensions of the original vector spaces $$A$$ and $$B$$ are *multiplied* together to yield the dimension $$d_P=d_A \times d_B$$ of the tensor product space.

So this is why when we have one qubit, we have a 2-dimensional Hilbert space, but when we have $$n$$ qubits, we have a $$2^n$$ dimensional Hilbert space. As the saying goes, Hilbert space is a big place!

---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/109754247164648030){:target="_blank"}

