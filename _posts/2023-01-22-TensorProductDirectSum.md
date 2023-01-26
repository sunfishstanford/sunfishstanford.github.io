---
layout: post
usemathjax: true
categories: [math, physics]
title: "Tensor product space vs direct sum space"

# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab
---

Cartesian space
3 dim, 3 indep basis vectors
Take each vector, as part of its own spanned space
Construct a new space where you take formal sum of linear combinations of the vectors
This is a direct sum space
So the dimensions are added together 

Now take two qubits. Each has a 2 dim state space, each state space spanned by 2 basis vector (eg, up and down). So there are a total of 4 basis vectors. To construct a state space that includes both qubits, you cannot make a linear combination of the 4 basis vectors, because they live in different spaces and cannot be added. 

but what does it mean to do a formal linear combination?

It means that you take the list of coefficients from the two spaces and treat them as two column vectors, and then you concatenate the two column vector to form a new column vector that has dimension equal to the sums of the two original dimensions.

what does it mean to do a direct product of the two spaces?
it means that for every v \in V and w \in W, you get an element of V X W by specifying both v and w.





It's interesting to view chemistry and biology through the lens of software and APIs. [Wikipedia defines an application programming interface](https://en.wikipedia.org/wiki/API){:target="_blank"} as a way for software programs to communicate with each other via well defined rules (protocols), so that a service provider, whose API is being called, can provide a service while hiding the details of the implementation so that the service consumers don't need to worry about those details. This enhances modularity and composability of a software system.

Similar principles apply to chemistry and biology! Certain chemical functional groups can be viewed as a type of API because we see the same functions being leveraged by many processes in a modular, composable way. A great example is a phosphate group, a phosphorus atom bonded to four oxygen atoms:

![Phosphate group](/assets/images/phosphate.png){: width="100" .center-image }

In molecules such as ATP that contains phosphate groups, the linkage between two phosphorus atoms and the connecting oxygen atom is kinetically stable (e.g., the ATP molecule is stable in the cell), but thermodynamically unstable (it is energetically favorable to break the bond to replace with a more thermodynamically stable configuration and thus release energy, e.g, hydrolysis of ATP). Also, a phosphate group tends to be negatively charged. 

Together, these factors enable a large variety of biochemical "use cases" where energy needs to be controllably stored or released (ATP as the "energy currency of cells"), or charge needs to be controllably added or removed (kinase/phosphatase to add or remove charge to proteins and thereby switch on/off their functions). And phosphate groups are a sort of "modular molecular API" that is used by these biochemical processes.

Here is a great discussion of [the importance of phosphates to life as we know it](https://chem.libretexts.org/Bookshelves/Organic_Chemistry/Book%3A_Organic_Chemistry_with_a_Biological_Emphasis_v2.0_(Soderberg)/09%3A_Phosphate_Transfer_Reactions/9.01%3A_Prelude_to_Phosphate_Transfer_Reactions){:target="_blank"}. Hint: be sure to read until the end of the page.

Useful Links
------------

1. Tim Soderberg's online text, *Organic Chemistry with a Biological Emphasis*: [Chapter on Phosphate Transfer Reactions](https://chem.libretexts.org/Bookshelves/Organic_Chemistry/Book%3A_Organic_Chemistry_with_a_Biological_Emphasis_v2.0_(Soderberg)/09%3A_Phosphate_Transfer_Reactions){:target="_blank"}

---

[Comment on Mastodon](https://hachyderm.io/@Sunfishstanford/109624369727398121){:target="_blank"}
