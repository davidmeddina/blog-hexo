---
title: Arrow Functios JS
date: 2019-07-24 13:24:15
tags:
---
Arrow functions – also called “fat arrow” functions, from CoffeeScript (a transcompiled language) — are a more concise syntax for writing function expressions. They utilize a new token, =>, that looks like a fat arrow. Arrow functions are anonymous and change the way this binds in functions.

Arrow functions make our code more concise, and simplify function scoping and the this keyword. They are one-line mini functions which work much like Lambdas in other languages like C# or Python. (See also lambdas in JavaScript). By using arrow functions, we avoid having to type the function keyword, return keyword (it’s implicit in arrow functions), and curly brackets.

```javascript
var materials = [
  'Hydrogen',
  'Helium',
  'Lithium',
  'Beryllium'
];

console.log(materials.map(material => material.length));
// expected output: Array [8, 6, 7, 9]
```

### How Much Use Is There for Arrow Functions?
Arrow functions have been called one of the quickest wins with ES6. Developer Lars Schöning lays out how his team decided where to use arrow functions:

- Use function in the global scope and for Object.prototype properties.
- Use class for object constructors.
- Use => everywhere else.

Arrow functions, like let and const, will likely become the default functions unless function expressions or declarations are necessary. To get a sense for how much arrow functions can be used, Kevin Smith, counted function expressions in various popular libraries/frameworks and found that roughly 55% of function expressions would be candidates for arrow functions.

Arrow functions are here: they’re powerful, concise, and developers love them. Perhaps it’s time for you to start using them!

[Taken from here](https://www.sitepoint.com/es6-arrow-functions-new-fat-concise-syntax-javascript/)

