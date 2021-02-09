# Fundamentals: Hoisting

"Hoisting" refers to the fact that in Javascript, certain kinds of things are evaluated "out of order".

## Functions

When you define a function with the `function` keyword, it is hoisted to the top.

```js
// The function declaration is pushed to the top.
// This snippet of code will not break.
hello();

function hello() {
  console.log('hi!');
}
```

## Variables

```js
// what will output to the console?
console.log(greeting);
let greeting = 'Hello';

// a. 'Hello'
// b. undefined
// c. ReferenceError: Cannot access 'greeting' before initialization
```

The answer is (c). Using `let` and `const` will prevent hoisting. _This is a good thing._ we should always write code in a logical fashion and using variables before they are declared can lead to some extreme spaghetti code. `var` is "half-hoisted". But since we aren't learning `var`, we don't need to focus on it.

## Anonymous functions

What happens if we assign a function to a variable?

```js
myGreeting();

let myGreeting = function() {
  console.log('hi')
}

// ReferenceError: Cannot access 'myGreeting' before initialization
```