# 2 - Utilizing `Object.create()`

## Overview
In the last chapter we used object literals and a factory function to create multiple object instances of "circle sprite" objects.

The code we wrote worked fairly well because the objects we created were very similar to one another (other than `color` and `radius`).

But what if we wanted to create a new kind of sprite object that:
- looks different, for example a "rectangle sprite" or an "image sprite"?
- moves differently, for example a "wrapping sprite" that wraps around the screen rather than bouncing, or a sprite that moves along a sine wave, or a "seeking sprite" that pursues other sprites?

Because these sprite variations are sharing a lot of state and behavior, it is a best practice to factor out that common code and put it someplace that it can be shared by all of these object variations.  In a class-based language we might define a superclass named `Sprite`, and then another class that derives or inherits from it named `CircleSprite`.

It is then fairly easy to define more subclasses such as `WrappingSprite`, `ImageSprite`, `SeekingSprite` and so on. These classes would inherit large amounts of state and behavior from `Sprite`, and then override `move()` and/or `draw()` as necessary.

In JavaScript however, we do not have classes or object-oriented inheritance, we instead have JavaScript's *prototype-based inheritance* as a way to override or extend object behavior. 

How do we do this in JavaScript? Read below!


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

```
let vehicle = {
  year: 2018,
  numWheels: 4,
  move(){
    console.log("Moving the vehicle now");
  }
};

```

**Gives us this in the debugger:**

![Screenshot](_images/canvas-sprites-object-create-1.jpg)


## <a id="section2">II. `Object.create()`








<hr><hr>

**[Previous Chapter <- Intro to Canvas Sprites (chapter 1)](canvas-sprites-1.md)**
