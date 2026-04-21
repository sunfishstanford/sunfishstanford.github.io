---
layout: post
usemathjax: true
categories: ['embracing transitory confusion', math]
title: "Memorizing the result for Gaussian integrals"
permalink: /:year/:title:output_ext



# note: shift-cmd-v to view the markdown view; cmd-k v to view side-by-side, then can do 'toggle preview locking' command in the 3 dots in the preview tab

---

I too would like to write down the result of a Gaussian integral by inspection...so this is an attempt to make it easier to do that.

Start with the following:

$$
\begin{aligned}
a x^2 + bx +c &= a\left[\frac{ax^2 + bx + c}{a}\right] \\
&= a\left[\frac{4a^2x^2 +4abx + 4ac}{4a^2}\right] \\
&= a\left[\frac{(b+2ax)^2}{4a^2}-\frac{b^2-4ac}{4a^2}\right] \\
&= a\left[(x+\frac{b}{2a})^2-\frac{b^2-4ac}{4a^2}\right] \\
&= a(x+\frac{b}{2a}-\frac{\sqrt{b^2-4ac}}{2a})(x+\frac{b}{2a}+\frac{\sqrt{b^2-4ac}}{2a})
\end{aligned}
$$

Therefore, setting $$c=0$$,

$$
\begin{aligned}
a x^2 + bx &= a\left[(x+\frac{b}{2a})^2-\frac{b^2}{4a^2}\right] \\
&= a(x+\frac{b}{2a})^2-\frac{b^2}{4a}
\end{aligned}
$$

So the key thing to remember is that the quadratic term has coefficient

$$
\boxed{a}
$$

and the constant term is

$$
\boxed{-\frac{b^2}{4a}}
$$

And the rationale is that factoring out $a$ gives a monic quadratic, which can be factored into the product of $x$ minus the two roots, and of course the coefficient of $x^2$ remains $a$. Since the two roots are something plus/minus the discriminant over $2a$, the product must contain the negative discriminant squared over $4a^2$, which when multiplied back with $a$ gives the negative discriminant squared over $4a$. And the discriminant squared is just $b^2$ because $c=0$.

We know that

$$
\begin{aligned}
\int_{-\infty}^{\infty} d^2x\, e^{-x^2} &= \int_0^{2\pi}d\phi \int_0^{\infty}dr\,r \exp(-r^2)\\
&= \frac{-2\pi}{2}\exp(-r^2)|_0^{\infty} \\
&= \pi \\
&= \int_{-\infty}^{\infty} dx\, e^{-x^2}\int_{-\infty}^{\infty} dy\, e^{-y^2} \\
&= \left(\int_{-\infty}^{\infty} dx\, e^{-x^2}\right)^2
\end{aligned}
$$

Therefore,
$$
\int_{-\infty}^{\infty} dx\, e^{-x^2} = \sqrt{\pi}
$$

and

$$
\int_{-\infty}^{\infty} dx\, e^{-ax^2} = \sqrt{\frac{\pi}{a}} .
$$

Finally,

$$
\begin{aligned}
\int_{-\infty}^{\infty} dx\, e^{-(a x^2 + bx)} &= \int_{-\infty}^{\infty} dx\, \exp\left[-a(x+\frac{b}{2a})^2+\frac{b^2}{4a}\right] \\
&= \sqrt{\frac{\pi}{a}} \exp\left(\frac{b^2}{4a}\right)
\end{aligned}
$$

So the formula to memorize is

$$
\boxed{
    \int_{-\infty}^{\infty} dx\, e^{-(a x^2 + bx)}
= \sqrt{\frac{\pi}{a}} \exp\left(\frac{b^2}{4a}\right)
}
$$

And just remember that the exponent on the right side (the answer) must be positive because otherwise in the limit $a \to 0+$, the integral should diverge, but a negative exponent would give cause the right side to vanish.

---

[Share or comment on Mastodon](https://hachyderm.io/@Sunfishstanford/116441138212572131){:target="_blank"}

[Share or comment on Bluesky](https://bsky.app/profile/sunfishstanford.bsky.social/post/3mjyc6fwm6223){:target="_blank"}

[//]: # (Bing prompt: Convert the following text to latex format,  only putting the math equation parts between the latex delimiters, and using $$ for the latex delimiters for both math mode and display math mode.)


