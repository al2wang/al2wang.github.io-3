---
title: Use the law of thermodynamics to calculate equilibrium constant
date: 2022-11-17 19:54 +0800
categories:
- math
- chem
- physics
tags:
- differential equation
- calculus
- thermodynamics
layout: post
excerpt: 'A sequel to stoichiometry in chemistry and physics contest.'
math : true
toc : true
---

<p align="center">
    <img src="https://user-images.githubusercontent.com/104330029/203699885-5770e993-7fd2-4b68-b7c2-5a2d364a4076.png">
</p>

## Intro

This post serves as a sequel to our stoichiometry journey, providing us with a more crystal-clear explanation to the concentration equilibrium constant, \\(K_ c\\), which is kind of a "beyond excellence level" concept.

To begin with, we write Gibbs as a function of temperature \\(T\\), pressure \\(p\\), and extent of reaction \\(\xi\\) (in case it sounds a bit unfamiliar, this is a physical quantity solely used to describe a chemical process):

$$\mathrm dG=-S\mathrm dT+V\mathrm dp-A\mathrm d\xi.$$

where \\(A=0\\)  gives the chemical equilibrium condition, while \\(\left(\frac{\partial A}{\partial\xi}\right)_ {T,p}<0\\) gives the chemical equilibrium stability condition. It can be further incorporated as

$$\text dG=V\mathrm{d}p - S\mathrm{d}T+\sum_i\mu_i\text dn_i. $$

Do you notice the letter (or more precisely, notation) \\(\mu_ i\\) from the previous derivation? It is a rate constant determined by experimenting.

WLOG define \\(n_i=\kappa_ i \mathrm d \xi\\), where stoichiometry number \\(\kappa_ i = a_ i \text{ or } b_ i\\), basically. Thus, \\(\text dn_ i=\kappa_ i\text d\xi\\). Assuming that the condition is constant temperature and pressure,

$$\text dG=0, \quad \textstyle \sum_ i\mu_ i\text dn_ i=0, $$

or simply \\(\sum_ i \mu_ i \kappa_ i = 0\\).

Now, it's time for us to introduce the three Le Chatelier principles below.

## Principle #1

"When the temperature is raised, the reaction equilibrium moves in the direction of endothermic."
{: .message}

Note that  \\(G\\)  is a non-standard  Legendre transform of \\(H\\)  to \\(S\\), so there is

$$ H=G-T\left(\frac{\partial G}{\partial T}\right)_{p,\xi}. $$

Thereby,

$$ \left(\frac{\partial G}{\partial T}\right)_ {p,\xi}=\frac{G-H}{T}. $$

Diverge the two sides of the above equation to \\(\xi\\)  to obtain

$$ \left(\frac{\partial^2G}{\partial T\partial\xi}\right)_ p=\left(\frac{\partial}{\partial\xi}\left(\frac{G-H}{T}\right)\right)_ {T,p}
=\frac{-A}{T}-\frac{1}{T}\left(\frac{\partial H}{\partial\xi}\right)_ {T,p}. $$

Under chemical equilibrium conditions, \\(A=0\\). And thus,

$$ \left(\frac{\partial^2G}{\partial T\partial\xi}\right)_p=-\frac{1}{T}\left(\frac{\partial H}{\partial\xi}\right)_{T,p}. $$

On the other hand,

$$\left(\frac{\partial^2G}{\partial\xi\partial T}\right)_ p = -\left(\frac{\partial A}{\partial T}\right)_{p,\xi}.$$

Therefore,

$$ \left(\frac{\partial A}{\partial T}\right)_ {p,\xi}=\frac{1}{T}\left(\frac{\partial H}{\partial\xi}\right)_ {T,p}. $$

Again,

$$ \left(\frac{\partial\xi}{\partial T}\right)_ {A,p}=-\frac{\left(\frac{\partial A}{\partial T}\right)_ {p,\xi}}{\left(\frac{\partial A}{\partial\xi}\right)_ {T,p}}=-\frac{\frac1T\left(\frac{\partial H}{\partial \xi}\right)_ {T,p}}{\left(\frac{\partial A}{\partial\xi}\right)_ {T,p}}. $$

Thus, when \\(\left(\frac{\partial H}{\partial\xi}\right)_ {T,p}>0\\) (i.e. positive reaction endothermic), \\(\left(\frac{\partial\xi}{\partial T}\right)_ {A,p}>0\\) (i.e. heating causes the positive reaction to proceed).

## Principle #2

"When pressurized, the reaction equilibrium shifts towards volume reduction."
{: .message}

First things first, we have Maxwell relations

$$ \left(\frac{\partial^2G}{\partial p\partial\xi}\right)_ {T}=-\left(\frac{\partial A}{\partial p}\right)_ {T,\xi}=\left(\frac{\partial V}{\partial\xi}\right)_ {T,p}, \tag ※$$

and this allows

$$ \left(\frac{\partial\xi}{\partial p}\right)_{A,T}=-\frac{\left(\frac{\partial A}{\partial n}\right)_{T,n}}{\left(\frac{\partial A}{\partial\xi}\right)_{T,p}}=\frac{\left(\frac{\partial V}{\partial\xi}\right)_{T,p}}{\left(\frac{\partial A}{\partial\xi}\right)_{T,p}}. $$

Thus, when \\(\left(\frac{\partial V}{\partial\xi}\right)_ {T,p}>0\\) (i.e. the forward reaction increases the volume), \\(\left(\frac{\partial\xi}{\partial p}\right)_ {A,T}<0\\) (i.e. pressurization will causes the inverse reaction to happen).

From equation \\((※)\\) we can derive that

$$\frac{\partial \mu_i}{\partial p}=\frac{\partial V}{\partial \xi_i}.$$

Put together with the equation of state \\(pV=nRT\\), there is

$$\frac{\partial \mu_i}{\partial p}=\frac{RT}{p}.$$

Then, we can integrate eqn. \\((※)\\) from the initial state \\(p^\ominus\\) to the equilibrium state \\(p_ i\\),

$$\Delta \mu_i = \mu_i - \mu_i^\ominus = \int^{p_i}_{p^\ominus}\frac{RT}{p}~\mathrm{d}p = RT\ln\frac{p_i}{p^\ominus}. $$

Substitution to this intricate integral will be

$$\begin{align} \sum_i\mu_i\kappa_i &=RT\sum_i \kappa_i\ln\frac{p_i}{p^\ominus}+\sum_i \mu_i^\ominus\kappa_i\\ &=RT\ln\prod_i\left(\frac{p_i}{p^\ominus}\right)^{\kappa_i}+\Delta G^\ominus, \end{align} $$

namely,

$$ \boxed{\ln\prod_i\left(\frac{p_i}{p^\ominus}\right)^{\kappa_i}=-\frac{ \Delta G^\ominus}{RT}}. $$

Consider the situation under the standard condition, where \\(p^\ominus = 1\\), then the partial pressure equilibrium constant \\(K_ p\\) that we often encounter in middle school AP Chem is

$$ K_p=\prod_ i p_ i^{\kappa_ i}. $$

Apparently, it has something to do with concentration as well. If we now bring in Dalton's Law of partial pressure, \\(p=\textstyle \sum p_i\\), we will be able write it out as well \\(p_i=n_i p/n\\).

Then, it can be rephrased as

$$ \boxed{K_c=\prod_i c_i^{\kappa_i}}. $$

This exactly boils down to what we are familiar within AP Chemistry---the `Concentration Equilibrium Constant`.

## Principle #3

"When a reactant is added, the reaction equilibrium shifts in the direction of reducing this reactant."
{: .message}

Since \\(\nu_i\mathrm  d\xi=\mathrm dn_i\\), there is

$$ \left(\frac{\partial A}{\partial\xi}\right)_{T,p}=\nu_i\left(\frac{\partial A}{\partial n_i}\right)_{T,p},\qquad i=1,2,\dots$$

Thus, when \\(\nu_i<0\\) (i.e. the positive reaction reduces reactant \\(i\\)), \\(\left(\frac{\partial A}{\partial\xi}\right)_ {T,p}>0\\) (i.e. increasing substance \\(i\\) causes \\(A>0\\), so that the reaction proceeds in a positive direction). \\(\quad □.\\)
