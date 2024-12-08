---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math]
title: "Why irreducible representations are orthogonal"
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


Take a nonzero vector in the vector space. Take a group element and have it act on the vector to produce another vector. Then take another group element and have it act on this new vector. If we repeat this for all the group elements and keep cycling through the group elements, then the vector space spanned by all of these vectors is an invariant subspace ("invariant" means that the subspace is closed under the actions of the group elements). Call this invariant subspace $$V$$.

Now, consider a linear operator $$A$$ defined on $$V$$, which means that $$A$$ acting on any vector in $$V$$ produces another vector in $$V$$. Then $$A$$ has a kernel, which is the set of vectors in $$V$$ that are mapped to $$0$$ by $$A$$. We can easily show that the kernel of $$A$$ is a subspace of $$V$$.

Next, suppose that $$A$$ commutes with all the group elements. Then, if we take any vector in the kernel of $$A$$, and apply any group element to the vector, the result will still be in the kernel of $$A$$. This is because applying the group element and then $$A$$ is the same as applying $$A$$ and then the group element (because they commute), and applying $$A$$ gives us $$0$$, and then applying the group element gives us $$0$$ again, which means that applying the group element to the vector gives us a vector that is still in the kernel. This means that under this commutation assumption, the kernel of $$A$$ is an invariant subspace.

Given that $$V$$ is an invariant subspace, we conclude that either the kernel of $$A$$ is equal to $$V$$, or the kernel of $$A$$ is just the zero vector. 

Now assume $$A$$ is Hermitian. (If it is not, it can be split up into a sum, $$A = A_1 + i A_2$$, where $$A_1 = (A+A^\dagger)/2$$ and $$A_2 = (A-A^\dagger)/(2i)$$, and then the logic here can be separately applied to $$A_1$$ and $$A_2$$.) Then the eigenvectors of $$A$$ form a basis for $$V$$. 

Take any eigenvalue $$\lambda_i$$ and form a new operator $$M_i=A-\lambda_i I$$, where $$I$$ is the identity operator. The kernel of $$M_i$$ is the subspace spanned by the corresponding eigenvectors of $$A$$. $$M_i$$ also commutes with all the group elements, and the kernel of $$M_i$$ will either be $$V$$ or the zero vector. If we go through each of the eigenvalues, there must be exactly one eigenvalue $$\lambda_{i_0}$$ for which $$M_{i_0}$$ has a kernel that is $$V$$, and for all the other eigenvalues the M-kernels will only be the zero vector. This conclusion follows from the fact that $$A$$'s eigenvectors must form a basis for $$V$$.

So now we see that the kernel of $$M_{i_0}$$ is $$V$$, which means that $$A-\lambda_{i_0} I$$ maps all vectors in $$V$$ to zero, which means that $$A=\lambda_{i_0} I$$. So $$A$$ must be a constant times the identity operator.


<details>
  <summary>Explanation</summary>  
  
that \(A-\lambda_{i_0} I\) maps all vectors in \(V\) to zero, which means that \(A=\lambda_{i_0} I\)

<details>
  <summary>\(\quad\)Explanation 2</summary>  
<p style="margin-left: 30px;">
So now we see that the kernel of \(M_{i_0}\) is \[V\], which means that $$A-\lambda_{i_0} I$$ maps all vectors in $$V$$ to zero, which means that $$A=\lambda_{i_0} I$$. So $$A$$ must be a constant times the identity operator.
</p>
</details>

</details>

[^1]: Based on the proof from Section 3.5 of *Group Theory for Physics* by Wu-Ki Tung. Simplified to emphasize the orthogonality aspect only.



---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/111993699873026393){:target="_blank"}



[//]: #  https://gist.github.com/pierrejoubert73/902cc94d79424356a8d20be2b382e1ab
