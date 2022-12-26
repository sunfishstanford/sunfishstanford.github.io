---
layout: post
usemathjax: true
categories: [math, physics]
title: "Confusion regarding tensors and transformations"
# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

So I was really getting confused about tensors and covariant versus contravariant transformations, but I think I understand it now, so I wanted to share this in case it's helpful for others.

For simplicity, let's just stick to a contravariant vector and a convariant 1-form. If we understand how that works, then we'll understand how a tensor transforms, since a tensor is just a linear combination of a bunch of tensor products of vectors and 1-forms.

***My initial confused thinking***
Under a coordinate transformation, a covariant vector has components that transform in the same way as the basis vectors. And a scalar is a quantity that is invariant under coordinate transformation. For example, see: [https://en.wikipedia.org/wiki/Covariance_and_contravariance_of_vectors](https://en.wikipedia.org/wiki/Covariance_and_contravariance_of_vectors).

Consider a specific point on a manifold, and an object \\(\partial_0 \equiv \frac{\partial}{\partial x^0}\\). When transformed to the primed coordinates, \\(\partial_{0} \rightarrow \partial_{0'} = \frac{\partial x^\mu}{\partial x^{0'}}\frac{\partial}{\partial x^\mu} \\). So it appears that \\(\partial_0\\) transforms as a **covariant vector**.

However, the same object can be written as \\(\partial_0 = V^\mu \partial_\mu\\), where \\(V^0=1\\) and the other 3 components of \\(V^\mu\\) are zero. This is evidently an invariant scalar, because we have raised and lowered indices that are matched. So \\(\partial_0\\) seems to be a **scalar**. This is a contradiction!

But there's more. This object \\(\partial_0\\) is in the tangent space \\(T_pM\\), which is known to be a vector space of contravariant vectors (namely, velocity vectors). Therefore, \\(\partial_0\\) seems also to be a **contravariant vector**!!

***The correct thinking***



