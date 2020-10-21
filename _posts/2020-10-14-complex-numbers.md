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

Hey folks, today I want to shed light on a really common topic in Mathematics, Complex Numbers, and particularly, the Euler's formula. Complex Numbers show up in many different fields, like signal processing, electromagetism, quantum mechanics and much more. Where the beginners become puzzled by basic questions such as "What's the meaning of $\sqrt{-1}$ ?" or "Does $\sqrt{-1}$ even exists?", even the experts, without grokking the intuition behind their properties, just get used to them. This may not be a major turn off, but viewing them from a different perspective makes us truly appreciate the beauty of Mathematics.

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

## Mathematical Operations

Common operations like addition, subtraction, multiplication apply to complex numbers as well. Adding add two complex numbers is fairly simple, you put the tail of the second complex number on the head of the first one, and see where the resulting head of two lands. Subtraction is easy as well. Subtracting a complex number $z = x_1 + iy_1$ from another complex number $w = x_2 + iy_2$ involves flipping the latter one and adding them. As it can be seen, this is like vector addition and subtraction, so to perform these two operations, you'd operate on real and imaginary part independently and combine the result.

### Multiplication

Here's where the things get interesting, because if you try to interpolate the analogy between complex numbers and vectors we've been making so far. It doesn't make sense, as vectors only have dot or cross products defined for them, whereas, an imaginary number, being $\sqrt{-1}$ follow rules of scalar multiplication. Strictly speaking, 

$$
a \times i = ai
$$

for any real number $a$.

Notice here, this is just like algebraic multiplication where you multiply a variable by a number, but, it's even more than that. Notice, on the argand plane, multiplying by $i$ rotates the point by $90^{\circ}$ anticlockwise. This is a valuable observation which we will make use of very often. If we start thinking multiplication by $i$ as $90^{\circ}$ rotation in counterclockwise direction, we can keep consistency between our observation and the fact that $i^2 = -1$ because that would essentially mean $1 \times i \times i$ which, in our context, means a $180^{\circ}$ rotation, which lands at $-1$. Now we can think multiplication by $n^{th}$ power of $i$ as $90 \times n$ degrees rotation in anticlockwise direction.

* INSERT A VERY COOL ANIMATION *

## Rotation by a certain angle $\theta$ 

So far we've looked at how multiplying a real number by $i$ rotates the original number by $90$ degrees. Now, I want to look at a more general case. For this, I ask a question, "By which complex number should I multiply $1$ to produce a $\theta$ degree rotation in counterclockwise direction?". You can work that out for yourself if you feel like it. The answer to this question is really simple, if we produced a rotation by $\theta$ degrees to unity, i.e. $1$, the real component of resulting complex number would be precisely $cos({\theta})$ and imaginary component $sin({\theta})$ for it to maintain its trajectory on the unit circle. So, the complex number that produces a rotation in anticlockwise direction to any complex number by $\theta$ degrees would be

$$
Z_{\theta} = cos({\theta}) + i sin({\theta})
$$

## The celebrity formula: $e^{i\pi} = -1$

The first thing that intrigues anybody who is seeing this formula is how does that even make sense. From the perspective of someone who is learning this formula for the first time, $e$ just means a real number that is about $2.71$, $\pi$ is another real number approximately $3.14$ and $i$ as usual, is $\sqrt{-1}$. Terms like $2^5$ or $10^6$ makes sense as they mean something. For example, $a^b$ means $b$ repeated multiplications of $a$. But expressions like $e^\pi$ cannot be explained in that way, because what would $\pi$ repeated multiplications even mean? And on top of that, when we start talking about expressions like $e^{i\pi}$, the level of complexity rises exponentially(no pun intended). This explanation doesn't make sense in our context.

The key to understanding this is viewing this from a different perspective. Consider a function $f(x)$ defined as:

$$
f(x) = 1 + \frac{x}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + ...
$$

Student of calculus will know that it's the taylor series expansion of exponential function, but that's a topic for a different day. Once again, this is a `definition` of $f(x)$, we don't question its origin, or what would it would evaluate to.

Now, let's start evaluating the values of this function for different values of $x$. Since we cannot compute the sum of infinite number of terms, we approximate the value of $f(x)$ by including only a few terms from beginning as the terms further away from beginning would be really small. Plugging in a few different values, we notice,

$$
f(1) = 1 + \frac{1}{1} + \frac{1}{2} + \frac{1}{6} + ... \approx 2.71828 = e\\
f(2) = 1 + \frac{2}{1} + \frac{4}{2} + \frac{8}{6} + ... \approx 7.38906 = e^2\\
f(3) = 1 + \frac{3}{1} + \frac{9}{2} + \frac{27}{6} + ... \approx 20.08554 = e^3\\
$$

Since, the function $f(x)$ satisfies the relation that $f(x) = e^x$ for real numbers, scientists and mathematicians started using $e^x$ as the shorhand symbol for the function $f(x)$ because writing $e^x$ is much easier than writing $3$ or $4$ terms of $f(x)$. So, $e^z$ is not $e$ raised to the power $z$, but rather syntactic sugar for this long function $f(x)$. That's why, we should tend to think of $e^{i\pi}$ not as $i\pi$ repeated multiplications of $e$, rather the function $f(x)$ evaluated at $i\pi$.
