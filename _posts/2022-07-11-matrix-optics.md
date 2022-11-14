---
layout: post
title: Matrix optics in high-level physics olympiad
author: Alex
date: 2022-07-11 22:18 +0800
tags: [physics, linear algebra, contest]
toc: true
mermaid: true
math: true
---

## Intro: How is matrix related to optics?

After knowing some of the fundamentals of modern optics, you should have a rough understanding of geometric optics (and maybe, more advanced, polarized optics). However, the common, traditional methods for geometric optics are basically a set of imaging formulae or special light mapping using geometric methods, the main point and main surface equivalent is also very tedious, in a bunch of lens imaging only one word: I will introduce a powerful tool rarely mentioned in the general competition tutorial: matrix optics. This article will introduce the content once and for all: matrix methods in geometric optics This article is based on the notes I made in reading the book Matrix Optics by Lu Yaxong Lu Baida. Part of the content will be directly excerpted from the book. Please bear with me for the poor drawing (I have a couple friends who are arguably \\(\rm{Ti}\it{k}\rm{Z}\\) god, but I don't feel like bothering them since they're extra busy at the time)... I'll try to explain matrix optics clearly with as few pictures as possible.

I'd like to start off by first introducing the expression of a beam of light in the \\( \textbf{polar coordinate} \\):

<blockquote style="border-left: 3px solid #ac95fc; color:#ac95fc; margin-bottom:2px"> <b>Theorem</b> (Function rotation).
  
Let \(f\) be the function you want to rotate and \(\theta\) be the angle counterclockwise from the \(x\)-axis you want to rotate it. Then the new function becomes

$$
\begin{pmatrix}
r \\
\theta
\end{pmatrix}
$$

</blockquote>








Look at this example:
<blockquote style="border-left: 3px solid #52a88e; color:#52a88e; margin-bottom:2px">
<b>Example</b>. This is an example.
</blockquote>

A definition:
<blockquote style="border-left: 3px solid #f79eb2; color:#f79eb2; margin-bottom:2px">
<b>Definition</b> (Cube). A <i>cube</i> is a six-faced 3D object.
</blockquote>

### Even smaller heading (H3)

#### Even smaller smaller heading (H4)

# Lists

## Ordered list

1. Apples
2. Bananas
3. Carrots

## Unordered list

- Chapter
  - Section
    - Paragraph

## Task list

- [ ] Do my physics HW
- [ ] Finish my english paper
  - [x] Find sources online
  - [ ] Write the paper
  - [ ] Pray
- [x] Do my math HW

## Description list

Sun
: the star around which the earth orbits

Moon
: the natural satellite of the earth, visible by reflected light from the sun

# Code

## Inline

This is an example of `inline code`.

## Code block

Regular block:

```
This is a common code snippet, without syntax highlight and line number.
```

Specific languages (e.g. Java):

```java
System.out.println("Hello world!");
```

# Miscellaneous

## Block quote

> This is a block quote.[^fn1]

## Tables

| Programming Language | Inventor         | Useful for          |
|:---------------------|:-----------------|--------------------:|
| Java                 | James Gosling    | Passing the AP      |
| Python               | Guido von Rossum | Training bots       |
| Wolfram Language     | Stephen Wolfram  | Doing your homework |

## Links

<https://yu-dylan.github.io/> or [click this](https://yu-dylan.github.io/).

## LaTeX

Powered by [MathJax](https://www.mathjax.org/):[^fn2]

$$ \sum_{n=1}^\infty \frac1{n^2} = \frac{\pi^2}{6} $$

> **Theorem** (Quadratic formula). Let $a\neq 0$. Then the two solutions to $ax^2 + bx + c = 0$ are given by
> 
> $$ x = \frac{-b\pm\sqrt{b^2-4ac}}{2a}. $$

## Citation

1. http://home.ku.edu.tr/~generalphysics/Phys206/Handouts/Matrix%20Optics.pdf
2. https://www.sfu.ca/~gchapman/e894/e894l6j.pdf

## Footnotes

[^fn1]: The footnote source
[^fn2]: The 2nd footnote source

