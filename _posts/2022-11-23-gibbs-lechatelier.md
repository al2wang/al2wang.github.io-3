---
title: Use thermodynamics to calculate equilibrium constant
date: 2022-11-23 19:54 +0800
categories:
- math
- chem
tags:
- chem
- partial differential eqns
layout: post
excerpt: 'What the heck?!'
math : true
toc : true
---

First, we write Gibbs as a function of temperature \\(T\\), pressure \\(p\\), and extent of reaction \\(\xi\\) (a physical quantity used to describe a chemical process):
$$ \mathrm dG=-S\mathrm dT+V\mathrm dp-A\mathrm d\xi. $$
where \\(A=0\\)  gives the chemical equilibrium condition, while \\(\left(\frac{\partial A}{\partial\xi}\right)_{T,p}<0\\) gives the chemical equilibrium stability condition.

Now, we introduce the three Le Chatelier principles below.

## Principle #1 

"When the temperature is raised, the reaction equilibrium moves in the direction of endothermic."
{ : message}

Note that  \\(G\\)  is a non-standard  Legendre transform of \\(H\\)  to \\(S\\), so there is
$$
H=G-T\left(\frac{\partial G}{\partial T}\right)_{p,\xi}.
$$ Thereby
$$
\left(\frac{\partial G}{\partial T}\right)_{p,\xi}=\frac{G-H}{T}.
$$ Diverge the two sides of the above equation to \\(\xi\\)  to obtain
$$
\left(\frac{\partial^2G}{\partial T\partial\xi}\right)_p=\left(\frac{\partial}{\partial\xi}\left(\frac{G-H}{T}\right)\right)_{T,p}
=\frac{-A}{T}-\frac{1}{T}\left(\frac{\partial H}{\partial\xi}\right)_{T,p}.
$$ Under chemical equilibrium conditions, \\(A=0\\). And thus,
$$
\left(\frac{\partial^2G}{\partial T\partial\xi}\right)_p=-\frac{1}{T}\left(\frac{\partial H}{\partial\xi}\right)_{T,p}.
$$ On the other hand, 
$$
\left(\frac{\partial^2G}{\partial\xi\partial T}\right)_p=-\left(\frac{\partial A}{\partial T}\right)_{p,\xi}.
$$ So,
$$
\left(\frac{\partial A}{\partial T}\right)_{p,\xi}=\frac{1}{T}\left(\frac{\partial H}{\partial\xi}\right)_{T,p}.
$$ Again,
$$
\left(\frac{\partial\xi}{\partial T}\right)_{A,p}=-\frac{\left(\frac{\partial A}{\partial T}\right)_{p,\xi}}{\left(\frac{\partial A}{\partial\xi}\right)_{T,p}}=-\frac{\frac1T\left(\frac{\partial H}{\partial \xi}\right)_{T,p}}{\left(\frac{\partial A}{\partial\xi}\right)_{T,p}}.
$$ Thus, when \\(\left(\frac{\partial H}{\partial\xi}\right)_{T,p}>0\\) (i.e. positive reaction endothermic), \\(\left(\frac{\partial\xi}{\partial T}\right)_{A,p}>0\\) (i.e. heating causes the positive reaction to proceed).

## Principle #2

"When pressurized, the reaction equilibrium shifts towards volume reduction."
{ : message}

First things first, we have Maxwell relationship
$$
\left(\frac{\partial^2G}{\partial p\partial\xi}\right)_{T}=-\left(\frac{\partial A}{\partial p}\right)_{T,\xi}=\left(\frac{\partial V}{\partial\xi}\right)_{T,p} .
$$ and this allows
$$
\left(\frac{\partial\xi}{\partial p}\right)_{A,T}=-\frac{\left(\frac{\partial A}{\partial n}\right)_{T,n}}{\left(\frac{\partial A}{\partial\xi}\right)_{T,p}}=\frac{\left(\frac{\partial V}{\partial\xi}\right)_{T,p}}{\left(\frac{\partial A}{\partial\xi}\right)_{T,p}}.
$$ Thus, when \\(\left(\frac{\partial V}{\partial\xi}\right)_{T,p}>0\\) (i.e. the forward reaction increases the volume), \\(\left(\frac{\partial\xi}{\partial p}\right)_{A,T}<0\\) (i.e. pressurization will causes the inverse reaction to happen).

## When a reactant is added, the reaction equilibrium shifts in the direction of reducing this reactant.

Since \nu_i\mathrm  d\xi=\mathrm dn_i, there is

\left(\frac{\partial A}{\partial\xi}\right)_{T,p}=\nu_i\left(\frac{\partial A}{\partial n_i}\right)_{T,p},\qquad i=1,2,\dots

Thus, when \nu_i<0 (i.e. the positive reaction reduces reactant i), \left(\frac{\partial A}{\partial\xi}\right)_{T,p}>0 (i.e. increasing substance  i  causes  A>0, so that the reaction proceeds in a positive direction).
