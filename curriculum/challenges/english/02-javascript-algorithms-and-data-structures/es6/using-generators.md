---
id: 587d7b87367417b2b2512b5f
title: Using Generators
challengeType: 1
---

## Description
<section id='description'>
Generator functions indicate where they can be paused using the `yield` keyword. If you have completed any of the debugging lessons, you can think of this as a breakpoint.
  
Being able to resume functions is incredibly useful when you need to run portions of a functon across code, but not all at once. 

Using what you learned in the last iterator lesson and the previous generator lesson, make an infinite generator that computes the Fibonacci sequence up to the fifth value.
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

function* fib() {
  while (true) {
    // start here!
  }
}

// you don't need to write the code to run it; we'll explain it more in depth later!
```

</div>

</section>

## Solution
<section id='solution'>

```js
function* fib() {
  let first = 1
  let second = 0
  while (true) {
  	let temp = first
    yield first 
    first += second
    second = temp
  }
}
```
</section>
