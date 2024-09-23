---
layout: post
usemathjax: true
categories: [math]
title: "Independent vectors and bases: a fun mental exercise for your next walk"
permalink: /:year/:title:output_ext

---

In linear algebra, we learn that we can choose *any* set of $$n$$ independent vectors from a $$n$$-dimensional vectors space $$V$$, and that set will be a basis for $$V$$. This is non-intuitive for me, and every once in a while, I realize that I've forgotten why this is so, and then have to re-learn it. So here is a quick-and-informal explanation with no equations that is hopefully easier to remember, and maybe it's also a fun exercise to see if you can recreate this while on a walk. It largely follows the explanation from Tom M. Apostol's *Calculus Volume II* (which *did* have many equations).

(Ok, so I cheated by using words to express some equations, but at least I don't have any complicated notation...)

Step 1: A $$k$$-dimensional space cannot have more than $$k$$ independent vectors
--------
We would like to prove this theorem: Any $$k+1$$ vectors (call these the "chosen vectors") from the vector space spanned by $$k$$ independent vectors must be dependent. We use induction, and start with the $$2$$ chosen vectors case. Then we prove that if the theorem holds for $$k$$ chosen vectors from a span of $$k-1$$ independent vectors, then it must hold for $$k+1$$ chosen vectors from a span of $$k$$ independent vectors.

The $$2$$ chosen vectors (chosen from the span of $$1$$ independent vector) case is trivial, as the span of a single vector consists of scalar multiples of the vector. And any two multiples are dependent.

For the $$k+1/k$$ proof when given the $$k/k-1$$ proof: 

Express the $$k+1$$ chosen vectors as linear combinations of the $$k$$ independent vectors. This gives us a $$(k+1)$$ x $$k$$ matrix. In each row of the matrix, the numbers in the $$k$$ columns are the coefficients for the $$k$$ independent vectors. If the first column of the matrix is completely zeros, that would mean that the $$k+1$$ chosen vectors are taken from the span of just $$k-1$$ independent vectors, and via the $$k/k-1$$ proof we see that the $$k+1$$ chosen vectors must be dependent. 

Therefore, let's assume that the first column is not completely zeros. Take one of the rows that is non-zero in the first column, and re-order things so that it becomes the first row in the matrix. Subtract some multiple of that row from all other rows, Gaussian-elimination style, so that all the other rows have zero in the first column. Each of those rows initially represented a chosen vector being equal to a linear combination of $$k$$ independent vectors. After the Gaussian-elimination phase, since we zeroed-out the first number and now only have at most $$k-1$$ non-zero numbers in a given row, that row now represents a linear combination of $$k-1$$ independent vectors, being equal to the chosen vector for that row minus a multiple of the chosen vector for the first row.

So this means that, considering the $$k$$ rows that now have a zero in the first column, we have $$k$$ vectors from the span of $$k-1$$ independent vectors. By applying the $$k/k-1$$ proof, we see that we must be able to construct a nontrivial representation of $$0$$ with those $$k$$ vectors. When we write out that nontrivial representation of $$0$$, we see that at least one of the chosen vectors from rows $$2$$ to $$k+1$$ must have a nonzero coefficient, and this proves that the set of $$k+1$$ chosen vectors is dependent.

Step 2:
--------
We would like to prove: given a $$n$$-dimensional vector space $$V$$ that has a basis $$B$$, we can choose *any* set $$C$$ of $$n$$ independent vectors from $$V$$, and $$C$$ will be a basis for $$V$$.

Each vector in $$C$$ can be expressed as a linear combination of the basis vectors in $$B$$, so span($$C$$) is also spanned by $$B$$, so span($$C$$) is a subset of $$V$$.

Suppose for contradiction that $$V$$ includes a vector $$x$$ that is not in span($$C$$). Then the set constructed by adding $$x$$ to $$C$$ is a set of $$n+1$$ vectors that are independent. But this set is comprised of vectors from $$V$$, so we have $$n+1$$ independent vectors from a $$n$$-dimensional space, which is impossible, per Step 1 above. Therefore, $$V$$ is a subset of span($$C$$). 

Therefore, $$V$$ is the same as span($$C$$).

Therefore, any set of $$n$$ independent vectors chosen from $$V$$ is also a basis of $$V$$.


---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/113185140353237231){:target="_blank"}

