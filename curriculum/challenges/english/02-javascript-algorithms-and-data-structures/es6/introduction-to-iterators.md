---
id: 587d7b87367417b2b2512b5e
title: Introduction to Generators
challengeType: 1
---

## Description
<section id='description'>
Throughout the entirety of freeCodeCamp, your experience with JavaScript functions has probably been consistent: a function goes all the way through once and then cleans itself up, clearing variables defined inside.
<br><br>
But what if you could pause a function, and pick back up in the same place later on?
  
Generators, one of the most anticipated additions in ES6, do just this. It also radically changes the syntax of JavaScript through the addition of `function*`, the proper way of defining a generator function.


</section>

## Instructions
<section id='instructions'>
Simply run the below code and check your console.
</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: Run the given code to move on.
    testString: assert(true, 'if you manage to mess this up delete your computer')
```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
function non_generator() {
  while (true) {
    return 1
    
    // you'll never be able to get here
    return 2
    return 3
  }
}

// take note of the "yield" keyword; it's the one thing you can't forget when defining a generator
function* generator() {
  while (true) {
    yield 1
    
    // yielding simply pauses or "yield"s the function, allowing it to be continued later
    yield 2
    yield 3
  }
}

const gen = generator()
for (let i = 0; i < 4; i++) {
  // notice the similarity between iterator and generator syntax; there's a reason for that
  console.log(non_generator(), gen.next().value)
}
```

</div>

</section>

## Solution
<section id='solution'>

```js
// ?!?!
```
</section>
