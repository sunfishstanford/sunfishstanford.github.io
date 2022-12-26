---
layout: post
usemathjax: true
categories: [math, physics]
title: "Confusion regarding tensors and transformations"
# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

So I was really getting confused about tensors and covariant versus contravariant transformations, but I think I understand it now, so I wanted to share this in case it's helpful for others.

For simplicity, let's just stick to a contravariant vector and a covariant 1-form. If we understand how that works, then we'll understand how a tensor transforms, since a tensor is just a linear combination of a bunch of tensor products of vectors and 1-forms.

**Some context**

Under a coordinate transformation, a covariant vector has components that transform in the same way as the basis vectors. And a scalar is a quantity that is invariant under coordinate transformation. For example, see: [https://en.wikipedia.org/wiki/Covariance_and_contravariance_of_vectors](https://en.wikipedia.org/wiki/Covariance_and_contravariance_of_vectors).

**My initial confused thinking**

Interpretation #1: Consider an object \\(\partial_0 \equiv \frac{\partial}{\partial x^0}\\) defined at a specific point on a manifold. When transformed to the primed coordinates, 

\\[
\partial_{0} \rightarrow \partial_{0'} = \frac{\partial x^\mu}{\partial x^{0'}}\frac{\partial}{\partial x^\mu}. 
\\]

 So it appears that \\(\partial_0\\) transforms as a *covariant 1-form* (because the primed coordinate is in the denominator of the Jacobian partial derivative).

Interpretation #2: However, this object \\(\partial_0\\) is in the tangent space \\(T_pM\\), which is known to be a vector space of contravariant vectors (namely, velocity vectors). Therefore, \\(\partial_0\\) also seems to be a *contravariant vector*!!

Interpretation #3: But there's more. The same object can be written as 

\\[\partial_0 = V^\mu \partial_\mu,\\]

 where \\(V^0=1\\) and the other 3 components of \\(V^\mu\\) are zero. This is evidently an invariant scalar, because we have raised and lowered indices that are matched. So \\(\partial_0\\) also seems to be a *scalar*!

**The correct thinking**

It turns out I was mixing up various closely related concepts. When we say that a vector transforms as a contravariant vector, what we really mean is that there is a vector that is a geometric object that is invariant, so when we look at it from different reference frames (coordinate systems), we need to ensure that the geometric object remains the same. So in the new frame, if the basis vectors transform a certain way, then the components must transform the inverse way. So a contravariant vector is a vector whose *components* transform in the contravariant way (with the primed coordinate in the numerator of the Jacobian partial derivative). The vector itself is not undergoing any changes, because it's invariant.

So some of these interpretations above got some things right and some things wrong. And Interpretation #2 actually got the right answer, which is that \\(\partial_0\\) is a contravariant vector. 

But remember that a geometric vector object doesn't transform–its components and bases are the ones that transform. So we need to write this in terms of its components and bases, and look at how they transform. 

\\(\partial_0\\) is in the tangent space \\(T_pM\\), which has bases \\(\partial_\mu\\). These bases transform as

\\[
\partial_{\mu} \rightarrow \partial_{\mu'} = \frac{\partial x^\nu}{\partial x^{\mu'}}\partial_\nu
\\]

And the components \\(V_\mu\\), defined via

\\[
\partial_0 = V^\mu \partial_\mu,
\\]

must transform in a contravariant way.

Note that these basis vectors transform as a basis set, from unprimed to primed coordinates. Writing the transformation for only \\(\partial_0\\) as done in Interpretation #1 does not make sense.

And finally, Interpretation #3 is pretty funny in terms of how it is wrong. In

\\[\partial_0 = V^\mu \partial_\mu,\\]

The subscript \\(\mu\\) in \\(\partial_\mu\\) is an index into the ordered basis set. It is *not* an index into the components of a vector. So for example, this index is used to return a specific vector, whereas an index for a component is used to return a specific real number. And so the Einstein summatio notation here is a convenient shorthand to do a linear combination of the bases weighted by the components, and it is *not* a contraction. A contraction is an inner product calculated via a dot product of covariant and contravariant components, with the raised and lowered indices to help us with bookkeeping, and this automatically ensures that the contraction is invariant. The linear combination of bases weighted by components, however, is *not* invariant.


