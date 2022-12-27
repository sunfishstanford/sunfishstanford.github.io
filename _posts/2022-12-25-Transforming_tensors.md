---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math, physics]
title: "Confusion regarding tensors and transformations"
# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

I was really getting confused about tensors and covariant versus contravariant transformations, but I think I understand it now, so I'd like to share this in case it's helpful for others.

For simplicity, let's just stick to a contravariant vector and a covariant 1-form. If we understand how that works, then we'll understand how a tensor transforms, since a tensor is just a linear combination of a bunch of tensor products of vectors and 1-forms.

Some context
------------

Under a coordinate transformation, a covariant vector has components that transform in the same way as the basis vectors. A contravariant vector has components that transform in the inverse way. And a scalar is a quantity that is invariant under coordinate transformation. For example, see: [https://en.wikipedia.org/wiki/Covariance_and_contravariance_of_vectors](https://en.wikipedia.org/wiki/Covariance_and_contravariance_of_vectors).

My initial confused thinking
----------------------------
updated


Interpretation #1: Consider an object $$\partial_0 \equiv \frac{\partial}{\partial x^0}$$ defined at a specific point on a manifold. When transformed to the primed coordinates, 

\\[
\partial_{0} \rightarrow \partial_{0'} = \frac{\partial x^\mu}{\partial x^{0'}}\frac{\partial}{\partial x^\mu}. 
\\]

 So it appears that \\(\partial_0\\) transforms as a *covariant 1-form* (because the primed coordinate is in the denominator of the Jacobian partial derivative).

Interpretation #2: However, this object \\(\partial_0\\) is in the tangent space \\(T_pM\\), which is known to be a vector space of contravariant vectors (namely, velocity vectors). Therefore, \\(\partial_0\\) also seems to be a *contravariant vector*!

Interpretation #3: But there's more. The same object can be written as 

\\[\partial_0 = V^\mu \partial_\mu,\\]

 where \\(V^0=1\\) and the other 3 components of \\(V^\mu\\) are zero. This is evidently an invariant scalar, because we have raised and lowered indices that are matched. So \\(\partial_0\\) also seems to be a *scalar*!

The correct thinking
--------------------

It turns out I was mixing up various closely related concepts. When we say that a vector transforms as a contravariant vector, what we really mean is that there is a vector, a geometric object, that is invariant. So when we look at it from different reference frames (coordinate systems), we need to ensure that the geometric object remains the same. So in the new frame, if the basis transform in a certain way, then the components must transform the inverse way. So a contravariant vector is a vector whose *components* transform in the contravariant way (with the primed coordinate in the numerator of the Jacobian partial derivative). The vector itself is not undergoing any changes, because it's invariant.

So some of these interpretations above got some things right and some things wrong.  Interpretation #2 actually got the right answer, which is that \\(\partial_0\\) is a contravariant vector. 

But remember that \\(\partial_0\\), as a geometric vector object, doesn't change under coordinate transformation–its components and basis are the ones that transform. So we need to examine its components and basis and how they transform. 

\\(\partial_0\\) is in the tangent space \\(T_pM\\), which has basis \\(\partial_\mu\\). These basis vectors transform as

\\[
\partial_{\mu} \rightarrow \partial_{\mu'} = \frac{\partial x^\nu}{\partial x^{\mu'}}\partial_\nu
\\]

And the components \\(V^\mu\\), defined via \\( \partial_0 = V^\mu \partial_\mu \\), must transform in a contravariant way.

Note that these basis vectors transform together as part of a basis set, from unprimed to primed coordinates. Writing the transformation for only \\(\partial_0\\) as done in Interpretation #1 does not make sense.

And finally, Interpretation #3 is pretty funny in terms of how it is wrong. In

\\[\partial_0 = V^\mu \partial_\mu,\\]

the subscript \\(\mu\\) in \\(\partial_\mu\\) is an index into the ordered basis. It is *not* an index into the components of a vector. So for example, this index is used to return a specific vector, whereas an index for a component is used to return a specific real number. And so the Einstein summation notation here is a convenient shorthand to do a linear combination of the basis vectors weighted by the components, and it is *not* a contraction. We write \\(\mu\\) as a lowered index to remind ourselves that it needs to be summed in conjunction with the raised index on the component. So the fact that \\(\partial_\mu\\) has a lowered index \\(\mu\\) *does not* mean that it is a covariant 1-form. There is a nice summary from David Kubiznak's online lecture on Relativity at the Perimeter Institute (see [page 43/95 of the slides](https://pdf.pirsa.org/files/18080039.pdf)):
\\[
\mathrm{dx}^\mu(\frac{\partial}{\partial x^\nu}) = \delta^\mu_\nu.
\\]

This means that the basis vectors for covariant 1-forms eat the basis vectors for contravariant vectors to return delta functions, and it's clear that \\(\partial_0\\) is a contravariant vector.

To finish this off, recall that a contraction is an inner product calculated via a dot product of covariant and contravariant components, with the indices raised and lowered to help us with bookkeeping, and this pairing of covariant and contravariant components automatically ensures that the contraction is invariant. The linear combination of basis vectors weighted by components, however, is *not* invariant.

Summary of learnings
--------------------

1. When we say that a vector transforms as a contravariant or covariant object, what we really mean is that there is a vector, a geometric object, that is invariant. And its components must transform when we change coordinate systems (reference frames) to ensure the vector stays the same.

2. A contravariant vector is a vector whose *components* transform in the contravariant way (with the primed coordinate in the numerator of the Jacobian partial derivative).

3. Basis vectors transform together as part of a basis set, when changing coordinate systems (reference frames). The point is that you'd like to know what the new basis vectors are in the new frame, so you express them in terms of the old basis vectors. So you are *not* saying that any single basis vector is *invariant* in some way.

4. In \\(V = V^\mu \partial_\mu,\\) the subscript \\(\mu\\) in \\(\partial_\mu\\) is an index into the ordered basis. It is *not* an index into the components of a vector.


5. A contraction is an inner product calculated via a dot product of covariant and contravariant components, with the indices raised and lowered to help us with bookkeeping.

6. The linear combination of basis vectors weighted by components, even though it uses a similar looking Einstein summation notation, is *not* invariant.

Useful Links
------------

1. David Kubiznak's course on (General) Relativity at the Perimeter Institute, 2018/2019. Starting in Lecture 4, he covers manifolds and a physicist's intro to differential geometry: <https://pirsa.org/C18021?page=1>

2. Sean Carroll's lecture notes on General Relativity (he also wrote a book on this that is widely used, including by the Kubiznak course above): <https://preposterousuniverse.com/wp-content/uploads/grnotes-one.pdf>. Eq. (1.26) on pdf page 16 explains how the vector is invariant under Lorentz transform, while its components in some coordinate system need to transform.


