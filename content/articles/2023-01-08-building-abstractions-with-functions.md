+++
date = "2023-01-08"
title = "Building Abstractions using Functions"
tags = ["abstractions", "zerone", "functional programming"]
katex = true
+++

If you have completed yet another 3-hour-long tutorial video on a new programming language and are well aware of basic concepts like variables, loops, functions, and arrays, but don’t know what to do next, well, this article is for you.

Let us begin with a wishful thinking. Don’t roll your eyes. Programming involves lots and lots of wishful thinkings. Assume that you’re an intern at a renowned company which specializes in numerical computation.

You’re assigned a task of creating a function that calculates the sum of integers through a lower and an upper limit. “That’s easy”, you say, and write something equivalent to this.

```js
function sumIntegers(a, b) {
	sum = 0
	while (a <= b) {
		sum += a
		a = a + 1
	}
	return sum
}
```
Days go by, and you're again instructed to write a function that accepts two integers, `a` and `b`, and returns the sum of cubes of integers from `a`through `b`. "Yet another easy task", you giggle and start typing again.

```js
function sumCubes(a, b) {
	sum = 0
	while (a <= b) {
		sum += Math.pow(a, 3)
		a = a + 1
	}
	return sum
}
```

The next day, your high school cousin asks you to help with her programming homework. Her homework involves writing a function that approximates the value of $\frac{\pi}{8}$ using an infinite series.

$$ \frac{\pi}{8} = \frac{1}{1 \cdot 3} + \frac{1}{5 \cdot 7} + \frac{1}{9 \cdot 11} + \ldots $$

You help her by writing a function.

```js
function piSum(a, b) {
	sum = 0
	while (a <= b) {
		sum += 1.0 / (a * (a + 2))
		a = a + 4
	}
	return sum
}
console.log(piSum(1, 50000))
```

The terminal prints `0.392696581698726`.It's approximately one-eighth of $\pi$. "Aha!", she smiles and you receive a thank.

You see, you repeated the same functionality thrice. It's not what programming is supposed to be. But, don't be disappointed, we all have made such mistakes at one point in time. Let's start by correcting it.

The pattern of all three functions you wrote is as follows

```
function name(a, b) {
	sum = 0
	while (a <= b) {
		sum += function of `a`
		lower = next value of `a`
	}
	return sum
}
```
Aha! You realize that you could write a `sum` function that is generic to all three scenarios.
```js
function sum(a, b, termFn, nextFn) {
	total = 0
	while (a <= b) {
		total += termFn(a)
		a = nextFn(a)
	}
	return total
}
```
This function takes two integers, `a`, `b`, the lower and upper limits, and two functions, one which calculates the current term in the sum, and the other one which calculates the new value of the iterator.

> Yes, functions can take other functions as arguments. That's one of the main points of this article. Almost all programming languages have such mechanism. Now, I'll show how you can create abstraction using functions.

This `sum` function we just wrote is equivalent to this mathematical expression.

$$  \sum_{i=a}^{b} f(a) $$

Not just that, our `sum` function is even more powerful than this, because it can skip iterations because of the `nextFn` argument. You'll see what that means in a while.

Let us consider writing the `sumIntegers` function using the sum function we have defined above.

```js
// a function that increments the given argument by 1
function increment(a) {
 return a + 1
}

// a function that returns returns its argument
function identity(a) {
 return a;
}

// sumIntegers function rewritten using sum
function sumIntegers(a, b) {
 return sum(a, b, identity, increment)
}
```

We call the sum function by specifying that the current term in the series is the element itself, and the next value of the iterator should be 1 more than the current value. Now we are building abstractions.

Since we will be passing the functions we define as the arguments to other functions frequently, we can use the arrow function notation provided by JavaScript ES6 and onwards. An expression of the form `(<args>) => {<body>}` is actually a function whose argument is `args` and body wrapped inside braces.

Now, back to our topic. We can re-write `sumCubes` function as

```js
function cube(a) {
 return Math.pow(a, 3)
}

function sumCubes(a, b) {
 return sum(a, b, cube, increment)
}
```

Just like the `sumIntegers` function, with a small exception being that the current term is the cube of the number rather than the number itself.

Alternatively, we can write it using the arrow function as follows:

```js
function sumCubes(a, b) {
  return sum(
    a,
    b,
    // function that calculates the cube of a number
    (number) => {
      return Math.pow(number, 3);
    },
    increment
  );
}
```

Here, instead of defining a function `cube` and passing it later, we directly defined the function where it was needed. Take a moment to digest this syntax. Compare the two implementations and make sure they're equivalent.

Let's also have a look at the refactored `piSum` function written using `sum`.

```js
function piSum(a, b) {
  return sum(
    a,
    b,
    // function that returns current term of the sum using iterator
    // verify that this is correct using the mathematical expression 
    // provided above
    (num) => {
      return 1.0 / (num * (num + 2));
    },
    // notice that in the mathematical expression above, the 
    // iterator in the denominator increase by 4 in each term
    (num) => {
      return num + 4;
    }
  );
}
```
This is the beauty of abstraction. A great degree of sophistication can be relatively easy if you know how to build abstractions properly. "How?", you ask. Remember when your high school teacher was vociferously reiterating that integral is just a fancy way of calculating a sum? Or, in the language of mathematicians,

$$ \int_{a}^{b} \[\ f(a + \frac{dx}{2}) + f(a + \frac{3dx}{2}) + f(a + \frac{5dx}{2})\ \]\ dx  $$

Let's see if he was right or not. Let's test it on a function the square root function.
```js
function integral(f, a, b, dx) {
  // calculate the sum inside square brackets
  const total = sum(a + dx / 2.0, b, f, (x) => {
    return x + dx;
  });
  return total * dx;
}

console.log(integral(Math.sqrt, 0, 4, 0.0001));
/* 5.333333394118553 */
```

$$ \int_{0}^{4} \sqrt{x}\ dx = \frac{16}{3} \approx 5.333  $$

![Yeah, Seience](/images/articles/building-abstractions/yeah_science.gif)

Wait, this only gets more interesting.

I hope you are aware of arrays in JavaScript. In real-world applications, it is often the case that we need to transform the elements of the arrays, for example, calculating the square of all the elements in that array, or filtering the elements based on some condition, or calculating a value based on all the elements of the array, e.g., the sum of all the elements, and so on and so forth.

Javascript provides a neat way of carrying out these operations. Consider this array

```js
let names = [
  "Adam",
  "Benjamin",
  "Hu",
  "Joe",
  "Lee",
  "Timothy",
]
```

Suppose we want to lowercase all the names in the array. One way of doing this is by writing a `for` loop that iterates through all the names and lowercases them one by one. A neat approach would be to make use of `map` function in JavaScript. The `map` function takes in a transformer function and applies it to all the elements of the provided array, thereby producing a new array. So `lowerCase` in the snippet below would be an array whose elements are the lowercased version of the names inside `names` array.

```js
let lowerCaseNames = names.map((name) => {
  return name.toLowerCase();
});
```
What if we want to filter out and keep only the names that are at least 5 letters long? We can achieve that using `filter` function provided by JavaScript.

```js
let longNames = names.filter((name) => {
  return name.length >= 5;
});
```

`filter` function takes in a predicate function and filters the array keeping only the elements that satisfy the predicate function. A predicate function is a function that should return a truthy or falsy value based on the element provided. So, for each name, the above expression checks if the length of the name is `>=5` and returns only those names which satisfy it.

Now, guess what this expression does.

```js
/* Tell me what this expression does */
let mystery = names
  .filter((name) => {
    return name.endsWith("e");
  })
  .map((name) => {
    return name.toUpperCase();
  });
```

This is only a bit more complicated. You can try it out on your browser console. Take your time.

It filters the array `names` keeping only the names ending with "e", and further converting to uppercase the elements of the filtered array. So, the result is `["JOE", "LEE"] `. You can chain such operations, thus creating a readable block of code and also achieving greater complexity.

Sigh! We built quite some abstractions there. Building abstraction using functions is an interesting topic in Computer Science. There is also a programming paradigm in CS called Functional Programing which involves building programs solely by applying and composing functions.

If you're interested in learning about this topic, you can explore further using these resources.

> [Structure and Interpretation of Computer Programs](https://www.amazon.com/Structure-Interpretation-Computer-Programs-Engineering/dp/0262510871)

> [Haskell Programming from First Principles](https://www.goodreads.com/en/book/show/25587599-haskell-programming-from-first-principles)

"Post proelium, praemium."