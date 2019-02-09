---
id: 587d7b87367417b2b2512b5b
title: Rationalizing Iterators
challengeType: 1
---

## Description
<section id='description'>
You're probably rather perplexed right now and that's OK! Iterators are strange they take something that JavaScript developers have been accustomed to since the start of the language and allow it to be modified in unusual ways. This isn't a bad thing though! Iterators have a lot going for them as many upcoming JavaScript features build upon them as well. We'll find out more about this in upcoming lessons.


Before we get to any of the cooler things we have to start small; <i>Iterables</i>. Iterables are functions that return Iterators and are stored in Object prototypes as <code>Symbol.iterator</code>. To introduce this syntax the hidden code of the previous lesson is now visible in the working area in a comment. If you are unfamiliar with the <code>this</code>-syntax or the concept of Constructors <a href='https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/object-oriented-programming/define-a-constructor-function'>this lesson</a> will help you out.

The setup is a little complicated; there's a lot of nesting involved so we're going to break it down line-by-line.

The first line defines the <code>RandList</code> constructor which takes one parameter <code>list</code>. The second line defines a property of the returned Object called <code>Symbol.iterator</code> (Note that Symbol.iterator is not a string it's a variable). This is where the relevant Iterator portion begins.

The next two lines are some initialization for iterating. <code>this.list</code> is the constructor input <code>list</code> shuffled around randomly and <code>this.index</code> is analogous to <code>x</code> in a C-style for loop (<code> for (let x = ...) { ... }</code>) which makes it easier to keep track of our randomized list.

Moving forward we hit our first return. Take note that the return is nested inside <code>this[Symbol.iterator]</code> and the function <code>RandList</code> does not return a value due to the definition of a constructor. The Iterator function returns an Object with a single method <code>next</code>. This function takes no parameters and increments <code>this.index</code> if the end of the list hasn't been reached. Take note of the structure of the returned Object <code>{ value: ... done: Boolean }</code> as this is <strong>crucial</strong> in getting your Iterator to work! If you forget to set <code>done</code> to <code>true</code> at the end, your iterator will run <strong><i>forever!</i></strong>

Understandably this example might seem like nothing more than an overcomplicated for-loop. This is oversimplification; Iterators lay the foundation for some incredibly powerful features.

</section>

## Instructions
<section id='instructions'>
Using the syntax below define a constructor <code>BackList</code> that takes an input <code>list</code> and iterates over it backwards. Remember to pay attention to where you place <code>this[Symbol.iterator]</code> and <code>next</code>. Use your previous knowledge of Arrays and JavaScript arithmetic to go back through the list you don't need a temporary variable to store the list in this scenario!
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
