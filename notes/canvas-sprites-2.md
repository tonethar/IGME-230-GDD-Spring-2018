# 2 - Utilizing `Object.create()`

## Overview
In the last chapter we used object literals and a factory function to create multiple object instances of "circle sprite" objects.

The code we wrote worked fairly well because the objects we created were very similar to one another (other than `color` and `radius`).

But what if we wanted to create a new kind of sprite object that:
- looks different, for example a "rectangle sprite" or an "image sprite"?
- moves differently, for example a "wrapping sprite" that wraps around the screen rather than bouncing, or a sprite that moves along a sine wave, or a "seeking sprite" that pursues other sprites?

### What if JavaScript had classes?
Because these sprite variations are sharing a lot of state and behavior, it is a best practice to factor out that common code and put it someplace that it can be shared by all of these object variations.  In a class-based language we might define a superclass named `Sprite`, and then another class that derives or inherits from it named `CircleSprite`.

It is then fairly easy to define more subclasses such as `WrappingSprite`, `ImageSprite`, `SeekingSprite` and so on. These classes would inherit large amounts of state and behavior from `Sprite`, and then override `move()` and/or `draw()` as necessary.

### But it doesn't!
In JavaScript however, we do not have classes or object-oriented inheritance, we instead have JavaScript's *prototype-based inheritance* as a way to override or extend object behavior. 

From https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain

**JavaScript objects are dynamic "bags" of properties (referred to as *own* properties). JavaScript objects have a link to a prototype object. When trying to access a property of an object, the property will not only be sought on the object but on the prototype of the object, the prototype of the prototype, and so on until either a property with a matching name is found or the end of the prototype chain is reached.**

How do we do override or extend object behavior in JavaScript? Read below!


## Contents
<!--- Local Navigation --->
I. [`Object.prototype`](#section1)

II. [`Object.create()`](#section2)

III. [???](#section3)

IV. [???](#section4)

V. [Review Exercise](#section5)


<hr>

## <a id="section1">I. `Object.prototype`

The `Object.prototype` property points at the *Object prototype object*. (what?)

What is a prototype object? Here is an excerpt from this MDN page: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype

*A typical object inherits properties (including methods) from Object.prototype, although these properties may be shadowed (a.k.a. overridden).*

*Changes to the Object prototype object are seen by all objects through prototype chaining, unless the properties and methods subject to those changes are overridden further along the prototype chain.  This provides a very powerful although potentially dangerous mechanism to override or extend object behavior.*


**Let's see what the default prototype object is on our simple `vehicle` object below. This code:**

**canvas-sprites-object-create-1.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Canvas Sprites - Object Create</title>
</head>
<body>
<script>
let vehicle = {
  year: 2018,
  numWheels: 4,
  move(){
    console.log("Moving the vehicle now");
  }
};

debugger;
</script>
</body>
</html>
```

**Gives us this in the debugger:**

![Screenshot](_images/canvas-sprites-object-create-1.jpg)

### I-A. Discussion

- above we see that the `year`, `numWheels` and `move` properties are on the main part of the object, and that under the `__proto__` property is the *prototype object*, which gives us the implicit build in properties (methods in this case) of `Object`. 
- if we try to access a property or method that does not exist on the main object, the property will be sought on that object's *prototype*. This is called the *prototype chain*. 

From https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain

*Each object has a private property which holds a link to another object called its prototype. That prototype object has a prototype of its own, and so on until an object is reached with null as its prototype. By definition, null has no prototype, and acts as the final link in this prototype chain.*

### I-B. An example of the prototype chain in action
So what do we get when we call `toString()` on `vehicle` like this:

`console.log(vehicle.toString());`

We get `[object Object]` in the console - which isn't too exciting, but indicates that `vehicle` "inherited" `toString()` from its prototype object.

### I-C. Property shadowing
You can use *property shadowing* to create a form of method overriding. Below we will give `vehicle` its own version of `toString()`, which will *shadow* the default implementation in the prototype object.

**canvas-sprites-object-create-2.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Canvas Sprites - Object Create</title>
</head>
<body>
<script>
let vehicle = {
  year: 2018,
  numWheels: 4,
  move(){
    console.log("Moving the vehicle now");
  },
  toString(){ // NEW
  	return "Year: " + this.year + ", numWheels: " + this.numWheels;
  }
};

console.log(vehicle.toString());
</script>
</body>
</html>
```

Which gives `Year: 2018, numWheels: 4` in the console, and confirms that vehicle's version of `toString()` shadowed the prototype's version.


## <a id="section2">II. `Object.create()`








<hr><hr>

**[Previous Chapter <- Intro to Canvas Sprites (chapter 1)](canvas-sprites-1.md)**
