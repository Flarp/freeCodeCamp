---
id: 587d7b87367417b2b2512b5d
title: Applications of Iterators
challengeType: 1
---

## Description
<section id='description'>
Believe it or not, many things you have worked with before hand can be used as iterators, and many of the new things introduced in ES6 are iterators too.
</section>

## Instructions
<section id='instructions'>
Before we move onto the next concept, take a look at the code below and see how iterators are used in the real world.
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
// Maps are Iterable
const iter_map = new Map([[1,2],[3,4]])
// notice the destructuring, remember how Maps work!
for (let [x, y] of iter_map) {
  console.log(x, 'and', y)
}

// Sets are Iterable
const iter_set = new Set([1,2,3,4])

for (let x of iter_set) {
  console.log(x)
}

// Regular Arrays are Iterable
const iter_array = [1,2,3,4]
for (let x of iter_array) {
  console.log(x)
}

// we can even steal a value from an array
const iterator_array = iter_array[Symbol.iterator]()
console.log(iterator_array.next().value)
```

</div>

</section>

## Solution
<section id='solution'>

```js
// ??
```
</section>
