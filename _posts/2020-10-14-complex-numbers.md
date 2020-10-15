---
title: "The elegence of complex numbers" 
toc: true
categories:
   - Mathematics
tags:
  - maths
  - complex numbers
  - euler's formula
header:
  teaser: ../assets/images/posts/euler.jpg
---

Hey folks, today I want to shed light on a really common topic in Mathematics, Complex Numbers. Complex Numbers show up in many different fields, like signal processing, electromagetism, quantum mechanics and much more. Where the beginners become puzzled by basic questions such as "What's the meaning of $\sqrt{-1}$ ?" or "Does $\sqrt{-1}$ even exists?", even the experts, without grokking the intuition behind their properties, just get used to them and continue working with them. This may not be a major turn off, but viewing them from a different perspective makes us truly appreciate the beauty of Mathematics.

## Introduction

Complex Numbers are essentially an extension to the Real Numbers. While it is possible to carry on with mathematics without ever needing to touch complex numbers, their properties is what led us to use them to make our live easier. You might have noticed that Complex Numbers show up almost all places where circular motion is directly or indirectly involved, for example, the analysis of simple harmonic motion or wave equations. This is not a coincidence, but rather a consequence of how complex numbers behave.

First, let's talk about imaginary numbers. The most basic imaginary number is $i$ which is `defined` to be $\sqrt{-1}$. Notice the stress on the word `defined`, meaning that $i$ is not a computed value. Let's derive a simple and useful property by extending this a step further.  

$$
i = \sqrt{-1}
$$ 

$$
i^2 = -1
$$

Now, I want to introduce a little geometry. To include imaginary numbers, we need to extend our traditional real number line, as shown below. The obtained plane is called Complex Plane, or Argand Plane. The number $i$ lies where the position $(0,1)$ would lie on an $x-y$ plane. Any number which take the form $x + iy$ is a complex number. The number $x$ is called the real part while $y$ is called the imaginary part of a complex number. Don't get carried away by the fact that the latter part is called 'imaginary', as you'll see in a while, it is every bit as real as any other numbers you can think of. In the diagram below, the number $z$ can be written as $z = 2 + 1i$

![Imaginary number](/assets/images/posts/complex_numbers/imaginary.png)  

*Picture experted from 3b1b Lockdown Math ep3*


