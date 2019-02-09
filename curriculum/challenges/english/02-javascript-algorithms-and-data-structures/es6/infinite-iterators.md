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
Create an array, <code>first_five</code>, and fill it with the first five <a href='https://wikipedia.org/wiki/Fibonacci_number'>Fibonacci numbers</a>, using the syntax we discussed above, making sure to use the two given variables, <code>first_var</code> and <code>second_var</code>. Remember, this iterator is infinite, so using <code>for..of</code> will crash your browser!
</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: Iterating over <code>BackList([1,2,3,4,5])</code> should return <code>[5,4,3,2,1]<code>.
    testString: assert(Array.from(new BackList([1,2,3,4,5])) === [5,4,3,2,1], JSON.stringify(test))
```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
/*
const RandList = function(list) {
  this[Symbol.iterator] = function() {
    this.list = randomize(list)
    this.index = 0
    return {
      next: () => {
        if (this.index === this.list.length) {
          return { done: true }
        } else {
          return { value: this.list[this.index++] done: false }
        }
      }
    }
  }
}
*/

const BackList = function(list) {
  this[Symbol.iterator] = function() {
    // your code here
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
// i havent done this in so long ill code the solution later
```
</section>
