---
id: 587d7b87367417b2b2512b5a
title: (Re)Introducing Iterators
challengeType: 1
---

## Description
<section id='description'>
In the lesson <a href=\"/javascript-algorithms-and-data-structures/basic-javascript/iterate-through-an-array-with-a-for-loop/\">Iterate Through an Array with a For Loop</a>, you learned how to use <i>iteration</i>, repeating a block of code multiple times, to process every element of an array. Before ES6, iteration was done using C-like for loops (<code>for (initial; final; increment) { ... }</code>) and while loops.
ES6 introduced a new kind of for loop, <code>for..of</code>. This new syntax not only provides a prettier way to iterate over arrays, it allows us to use a new feature added in ES6, called <i>iterators</i>.
<i>Iterators</i> allow you to customize how a certain object functions when being iterated over in a <code>for..of</code> statement.
Sometimes, code explains itself better than a human can, and this is one such case. 
</section>

## Instructions
<section id='instructions'>
Run the program and inspect the result in your browser console. (It's encouraged to run the program multiple times to see what's going on!)
</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: Run the given program.
    testString: assert(true, 'Run the given program')
```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
const rand_list = new RandList([0,1,2,3,4,5,6,7,8,9])
for (let y = 0; y < 3; y++) {
  for (let x of rand_list) {
    console.log(x)
  }
}
```

</div>

### Before Test
<div id="js-setup">
```js
// from https://stackoverflow.com/questions/2450954/how-to-randomize-shuffle-a-javascript-array
const horrid_shuffler = list => list.sort(_ => 0.5 - Math.random())
const RandList = function(list) {
  this[Symbol.iterator] = function() {
    this.list = horrid_shuffler(list)
    this.index = 0
    return {
      next: () => {
        if (this.index === this.list.length) {
          return { done: true }
        } else {
          return {value: this.list[this.index++] done: false }
        }
      }
    }
  }
}
```
</div>

</section>

## Solution
<section id='solution'>

```js
const rand_list = new RandList([0,1,2,3,4,5,6,7,8,9])
for (let y = 0; y < 3; y++) {
  for (let x of rand_list) {
    console.log(x)
  }
}
```
</section>
