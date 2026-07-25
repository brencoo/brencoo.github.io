---
layout: post
title: "The Underappreciated Assumption Behind Newtonian Determinism"
date: 2026-07-04 00:00:00 +0200
categories: physics math philosophy
math: true
---

I think of Newtonian mechanics as being deterministic in the Laplace's demon sense: if we knew the present state of the universe exactly, the laws of motion should let us perfectly reconstruct the past as well as predict the future.

However, for this to work there is a mathematical assumption that is, from my experience, often left implicit. I will first clarify the assumption and then present a nice thought experiment by John Norton on it.

## Nonlinear Dynamics Recap

In Steven Strogatz's book [*Nonlinear Dynamics and Chaos*](https://www.routledge.com/Nonlinear-Dynamics-and-Chaos-With-Applications-to-Physics-Biology-Chemistry-and-Engineering/Strogatz/p/book/9780813349107), one quickly encounters the existence and uniqueness theorem:

> **Existence and uniqueness theorem.** Consider the initial value problem $\dot x=f(x),\ x(0)=x_0$. If $f$ and $f'$ are continuous on an open interval containing $x_0$, then the initial value problem has a solution for some time interval around $t=0$, and that solution is unique.

He gives the nice example, characterized by

$$
\dot x = x^{1/3}, \qquad x(0)=0.
$$

The solution $x(t)=0$ is obvious. However, for any waiting time $T\ge 0$, the following is also a solution:

$$
x_T(t)=
\begin{cases}
0, & t \le T,\\
\left(\frac{2(t-T)}{3}\right)^{3/2}, & t \ge T.
\end{cases}
$$

We can easily see that the derivative

$$
f'(x)=\frac{1}{3}x^{-2/3}.
$$

blows up at $x=0$, thus not fulfilling the theorem. Norton's thought experiment translates this into the physical world.

## Norton's dome

In [Norton's own blog](https://sites.pitt.edu/~jdnorton/Goodies/Dome/), he constructs an idealized dome in a gravitational field. A point mass sits on its surface and friction is neglected. The dome is rotationally symmetric, and $r$ denotes the distance from the top measured along the dome's surface.


The dome is shaped so that, under gravity, the mass's radial motion obeys

$$
\ddot r = \sqrt r.
$$

Now we place the mass at the very top of the dome, at rest:

$$
r(0)=0, \qquad \dot r(0)=0.
$$

![Cross-section of Norton's dome with a ball at the apex.](/assets/images/nortons-dome-cross-section.png){: style="max-width: 75%; display: block; margin: 1.5rem auto;"}


Again, the obvious solution is $r(t)=0$. The mass simply stays at the top forever. However, this is not the only solution. For any waiting time $T\ge 0$,

$$
r_T(t)=
\begin{cases}
0, & t \le T,\\
\dfrac{(t-T)^4}{144}, & t \ge T
\end{cases}
$$

also satisfies the same equation of motion and the same initial state. The mass can stay at the top for an arbitrary amount of time and then start sliding down the dome.

This is really cool. It may feel as though Newton’s laws are being violated, but (as Norton argues) they are not. It starts as an ordinary high-school physics exercise, yet exposes "hidden" assumptions behind our classical expectations: Newton’s laws alone do not guarantee a unique solution. For that, we need additional regularity assumptions, such as the one in the theorem above.  For the technical details and some of the debate around the example, see [Norton’s original post](https://sites.pitt.edu/~jdnorton/Goodies/Dome/) or the [Wikipedia article](https://en.wikipedia.org/wiki/Norton%27s_dome).
