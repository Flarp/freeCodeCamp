---
id: 587d7b87367417b2b2512b5c
title: Infinite Iterators
challengeType: 1
---

## Description
<section id='description'>
In the last lesson, we were very careful to make sure our Iterator terminated.
  
<i>What if it doesn't?</i> What if we wanted an Iterator that goes on forever, constantly computing values only when we want it to? Can Iterators be paused, and returned to later?",

By using a little code inspection and some cleverness, we most certainly can! A little more code is required than our previous examples, but that's OK! We'll be able to use a neat shortcut later on, but for now, it's nice to see what we're actually doing under the hood.

Remember that for our previous examples used <code>new</code> to create the Object we wanted to iterate over fully. In order to iterate over partially, we need to go a tiny bit further.

First, we construct the Iterable as usual.
<code>const iterable = new FibIter()</code>

Next, we extract the Iterator inside into its own Object.
<code>let iterator = new iterable[Symbol.iterator]()</code>
Finally, we manually move the iterator forward using the <code>next</code> method defined in it. Since <code>next</code> returns an Object, we can access the value returned with the <code>value</code> property.
<code>iterator.next().value</code>

The syntax is undeniably a tad gross, but remember that shortcut we have coming up!

</section>

## Instructions
<section id='instructions'>
Create an array, <code>first_five</code>, and fill it with the first ten <a href='https://wikipedia.org/wiki/Fibonacci_number'>Fibonacci numbers</a>, using the syntax we discussed above. Remember that this iterator is infinite, so using <code>for..of</code> will crash your browser!
</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: <code>first_ten</code> should contain the first ten Fibonacci numbers.
    testString: assert(first_ten === [1,1,2,3,5,8,13,21,34], 'first_ten should have first ten fib numbers')
```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
const FibIter = function() {
  this[Symbol.iterator] = function() {
  this.first = 1
  this.second = 0
  this.started = false
  return {
    next: () => {
      if (!this.started) {
       this.started = true
        // the first two fib numbers are [1,1], this ensures it
        return { value: 1, done: false }
      }
      const temp = this.first
      this.first = this.first + this.second
      this.second = temp
      return { value: this.second, done: false }
      }
    }
  }
}
const first_ten = []
// const iterable = ...
// const iterator = ...
// code goes here
```

</div>

</section>

## Solution
<section id='solution'>

```js
const FibIter = function() {
  this[Symbol.iterator] = function() {
  this.first = 1
  this.second = 0
  this.started = false
  return {
    next: () => {
      if (!this.started) {
       this.started = true
        // the first two fib numbers are [1,1], this ensures it
        return { value: 1, done: false }
      }
      const temp = this.first
      this.first = this.first + this.second
      this.second = temp
      return { value: this.second, done: false }
      }
    }
  }
}

const iterable = new FibIter()
const iterator = new iterable[Symbol.iterator]()
const first_ten = []
for (let x = 0; x < 10; x++) {
	first_ten.push(iterator.next().value)
}
```
</section>
