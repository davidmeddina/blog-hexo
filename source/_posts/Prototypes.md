---
layout: understanding
title: Prototypes JS
date: 2019-07-25 15:17:42
tags:
---

Objects in JavaScript have an internal property known as prototype. It is simply a reference to another object and contains common attributes/properties across all instances of the object. An object’s prototype attribute specifies the object from which it inherits properties.

The Array object has a prototype Array.prototype and the object instance, num, inherits the properties of the Array object. This is why you can use a method like sort() on an array instance.

Same thing goes for other objects like Date(), String(), Function() etc.
When a constructor (a.k.a. pseudo classical inheritance) function is built, the newly created objects inherit the prototype properties of the constructor function and that’s the critical feature of constructors. They (constructor functions) are built for the initialization of newly created objects. Constructors are invoked using the new keyword.

```javascript
const Car = function(color, model, dateManufactured) {
this.color = color;
this.model = model;
this.dateManufactured = dateManufactured;
};
Car.prototype.getColor = function() {
return this.color;
};
Car.prototype.getModel = function() {
return this.model;
};
Car.prototype.carDate = function() {
return `This ${this.model} was manufactured in the year ${this.dateManufactured}`
}
let firstCar = new Car('red', 'Ferrari', '1985');
console.log(firstCar);
console.log(firstCar.carDate()); // à This Ferrari was manufactured in the year 1985.
```

From the example above, the carDate, getColor and getModel functions are properties of the Car object and instances of the Car object like firstCar can inherit all its properties.

### Prototype chain
When an object gets a request for a property that it does not have, its prototype will be searched for the property, then the prototype’s prototype, and so on. So who is the prototype of an object? It is the great ancestral prototype, the entity behind almost all objects, Object.prototype. Many objects don’t directly have Object.prototype as their prototype, but instead have another object that provides a different set of default properties. Functions derive from Function.prototype, and arrays derive from Array.prototype and so on.

That’s it for JavaScript prototypes. I hope you understand what they mean and how to use them.

Taken from [here](https://medium.com/backticks-tildes/javascript-prototypes-ee46810e4866)


