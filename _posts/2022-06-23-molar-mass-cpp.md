---
layout: post
title: Calculation of molar mass in C++
tags: mathjax cpp
math: true
date: 2022-06-24 22:35 +0800
---

世界上所有物质均可以用元素周期表中各元素组合表示。给定物质化学式，该如何用程序帮我们计算其摩尔质量 \\\(n\\\) 呢？

有两个比较难的点。

This course will cover the basic approaches and mindsets for analyzing and designing algorithms and data structures. Topics include the following: Worst and average case analysis. Recurrences and asymptotics. Efficient algorithms for sorting, searching, and selection. Data structures: binary search trees, heaps, hash tables. Algorithm design techniques: divide-and-conquer, dynamic programming, greedy algorithms, amortized analysis, randomization. Algorithms for fundamental graph problems: minimum-cost spanning tree, connected components, topological sort, and shortest paths. Possible additional topics: network flow, string searching.

Testing math:
<blockquote style="border-left: 3px solid #ac95fc; color:#ac95fc; margin-bottom:2px">
<b>Theorem</b> (Function rotation). Let $f$ be the function you want to rotate and $\theta$ be the angle counterclockwise from the $x$-axis you want to rotate it. Then the new function becomes

$$y\cos \theta-x\sin \theta=f\left(x\cos \theta+y\cos \theta\right).$$
</blockquote>

Look at this example:
<blockquote style="border-left: 3px solid #52a88e; color:#52a88e; margin-bottom:2px">
<b>Example</b>. This is an example.
</blockquote>

A definition:
<blockquote style="border-left: 3px solid #f79eb2; color:#f79eb2; margin-bottom:2px">
<b>Definition</b> (Cube). A <i>cube</i> is a six-faced 3D object.
</blockquote>


Testing math:
<blockquote style="border-left: 3px solid #ac95fc; color:#ac95fc; margin-bottom:2px">
<b>Theorem</b> (Function rotation). Let $f$ be the function you want to rotate and $\theta$ be the angle counterclockwise from the $x$-axis you want to rotate it. Then the new function becomes

$$y\cos \theta-x\sin \theta=f\left(x\cos \theta+y\cos \theta\right).$$
</blockquote>

Look at this example:
<blockquote style="border-left: 3px solid #52a88e; color:#52a88e; margin-bottom:2px">
<b>Example</b>. This is an example.
</blockquote>

A definition:
<blockquote style="border-left: 3px solid #f79eb2; color:#f79eb2; margin-bottom:2px">
<b>Definition</b> (Cube). A <i>cube</i> is a six-faced 3D object.
</blockquote>


Testing math:
<blockquote style="border-left: 3px solid #ac95fc; color:#ac95fc; margin-bottom:2px">
<b>Theorem</b> (Function rotation). Let $f$ be the function you want to rotate and $\theta$ be the angle counterclockwise from the $x$-axis you want to rotate it. Then the new function becomes

$$y\cos \theta-x\sin \theta=f\left(x\cos \theta+y\cos \theta\right).$$
</blockquote>

Look at this example:
<blockquote style="border-left: 3px solid #52a88e; color:#52a88e; margin-bottom:2px">
<b>Example</b>. This is an example.
</blockquote>

A definition:
<blockquote style="border-left: 3px solid #f79eb2; color:#f79eb2; margin-bottom:2px">
<b>Definition</b> (Cube). A <i>cube</i> is a six-faced 3D object.
</blockquote>

- social 30 review
- ASDAN certificate
- AIF + OSP + UBC
- math 30-1 module 6
- check ALL EMAILS!!!
- linkedin "demonstrate skills"

第一，元素周期表中表示元素的符号并不是固定长度。有用一个字母表示的，也有用两个字母表示的。这无疑增加了我们程序的判断难度；第二，在表示物质的时候，我们不仅要用字母，还有数字。而且，数字可以是多位的，也可以是一位的，比如\\\(C_{12}O_{12}, CO_2\\\)等。因此，我们需要通过判断连续数字的长度来确定某一个元素的个数。

根据问题的描述，首先，我们分析，表示一种元素最多有两个字母，而且如果是两个字母时候，必然是第一位是大写，第二位是小写，这其实告诉我们两个方面的信息，第一、判断一种元素的充要条件是开头是大写字母，因此程序在执行过程中，发现大写字母，就开始判断当前元素是哪一种。循环时，发现本次取出的是小写字母，直接跳过就可以了，因为，它已经跟随其前面的字母做过判断了，第二、就是告诉我们字符数组定义的长度为\\\(3\\\)以上，因为还有结束字符`\0`. 这也是我们这个问题的第一个关键点，元素判断。

第二个关键点，自然就是元素的个数是多少，事实上，我们在进行数字计算的时候，依然采用的是一位一位拿出来，每次都做成累加运算就ok。这也是一种经典的处理连续数字的方式，不过这里要注意运算时候不能拿ASCII码运算，要注意字符向数字的转化，一般都会注意。

其实我的程序思路很简单， 首先，过来一个字符串，我们利用`for`循环，将字符串的每一位拿出来，首先要做的是判断，判断是大写字母时，我们对其后面一位进行判断，如果后一位是小写字母，说明这个元素是用两位字母表示，否则就是用一位字母表示，而后，我们再用得到的一位或者两位的结果去查表，找出该元素在表中对应位置的下标，就找到了该元素的摩尔质量。这时候，就将该元素的摩尔质量加在总的物质的摩尔质量对应的变量。之所以这样处理，因为，只要某一种元素的字母出现在字符串中，说明，该元素在该物质中至少出现了一次，所以，先加上一次。

如果该物质中该元素有多个，那么其后肯定要跟大于\\\(2\\\)的数字，这个数字可能不止一位，因此，当发现某一位是数字字符的时候，就进入一个循环，计算连续数字表示的值是多少，这里也要注意ASCII码和数字的转化，跳出循环的条件是：不是数字字符，然后，将元素的摩尔质量与该数字减一后的结果相乘，然后累加到总的摩尔质量上，为啥是和该数字减一相乘呢，因为，我们前面说，当某个元素的字母出现时，我们就加了一次，如果只有一个该元素，默认是不用写数字的，所以，就不会有这一步操作，他们的结果是正确的，但是，如果是2个的话，就会紧跟着有2的角标，因此，我们需要有上述相乘累加的操作，但是，因为前面已经加过一次了，所以，要先减一，然后相乘相加。

最后面循环结束，输出结果。欢迎大家留言，讨论。

An inline math: \\\(E=mc^2\\\).

A display math:

$$
i\hbar \frac{\partial \Psi}{\partial t} = -\frac{\hbar^2}{2m}
\frac{\partial^2 \Psi}{\partial x^2} + V \Psi
$$

This is another equation:

$$
\mathrm e^{\mathrm i \theta} = \cos \theta + \mathrm i \sin \theta
$$

$$
 \boldsymbol{\mathbf{V}}  = 
 \begin{pmatrix}1 & x_1 & x_1^2 & \dots & x_1^{m-1}\\
1 & x_2 & x_2^2 & \dots & x_2^{m-1}\\
1 & x_3 & x_3^2 & \dots & x_3^{m-1}\\
\vdots & \vdots & \vdots & \ddots & \vdots\\
1 & x_n & x_n^2 & \dots & x_n^{m-1}\end{pmatrix} 
$$
