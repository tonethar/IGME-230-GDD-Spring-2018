# Final Exam Review

The exam is cumulative, so everything we have covered this semester is fair game. 

## I. Topics covered since midterm

### I-A. Intro to Web Apps
Most of this is new: https://github.com/tonethar/IGME-230-GDD-2017-Fall/blob/master/notes/web-apps-0.md

All of the content above is fair game. Be sure to look over the review questions and assignments for chapters 1-10


### I-B. Intro to PixiJS
https://github.com/tonethar/IGME-230-GDD-2017-Fall/blob/master/notes/pixi-js-0.md

**Major topics:**
- Factoids about PixiJS
- ES6 classes, constructors, inheritance, `this`
- CORS
- Sprite Hierarchy


### I-C. Weekly Notes
Week 8+ in [weekly](../weekly/) covers the newer material. 



## II. Concepts that may be tested

### CSS Selectors
Be able to write CSS rules using these selectors:
- universal,type,class,id
- descendant
- attribute
- selectors for button states

### The DOM & DOM Methods
- which DOM method have we been using to get a reference to a single element on a web page?
- which DOM method have we been using to get references to multiple elements on a web page?
- how do you set and get the attribute values of DOM elements?
- which method is used to add elements to the DOM tree?
- which method is used to remove elements from the DOM tree?

### Variables & Types
- is JavaScript a dynamically typed or statically typed language? What is the major difference between these types of languages?
- what does `"use strict"` do?
- how do you create a *block* in JavaScript?
- define what variable *scope* is.
- how are variables *scoped* when declared with `let` and `const`?
- how are variables *scoped* when declared with `var`?
- in regards to `let` and `const` declared variables, what is a "temporal dead zone" and how is it caused?
- are function *declarations* **hoisted** in JavaScript?
- are function *expressions* **hoisted** in JavaScript?
- give examples of JS reference types and JS value types.
- how does the behavior of `const` vary when dealing with (primitive) value types, as opposed to reference types?
- what is a *falsy* value?
- list JavaScript's 7 falsy values.

### Functions
- write a function named *addThem* that takes two arguments and returns their sum. Be sure you can write this both as a standard function, and as an ES6 arrow function.
- write a function (arrow or standard) named *addThem2* that takes two arguments and returns their sum. If either parameter is not passed in,  they will have default values of `0`.
- write a function that takes another function as an argument, and then calls that passed in function.

### Arrays
- <s>write a *testing function* for use with `array.filter()` that puts objects with a `.y` of less than -10 in the returned array</s>
- <s>write a *comparator function* for use with `array.sort()` that puts objects with a `.alive` value of `true` at the beginning of the array</s>
- give 3 ways to loop through an array
- how are JS *typed arrays* different from the standard JS `Array`

### Events
- compare and contrast *event handlers* and *event listeners*
- why will this line of code - `window.onload=init();` - fail? (assume that the `init()` function is correctly defined elsewhere)
- why will this line of code - `window.addEventListener("onload",init);` - fail? (assume that the `init()` function is correctly defined elsewhere)

### Classes & Objects
- create an object literal with at least 2 properties, and at least one method that acts upon those properties
- create an ES6 `class` with at least 2 properties, and at least one method that acts upon those properties
- what is the keyword used when a JS class inherits from another JS class?
- which `Object` static method is used to prevent an object from having new properties added to it?
- which `Object` static method is used to prevents an object from having new properties added to it, and also prevents the values of those properties from changing?
- which JS methods are used to *serialize* and *deserialize* objects?

### Web Services (these are in the notes, and in Wikipedia)
- define *Ajax*
- define *web service*
- define *API Key*
- define *Query String*

### Acronym Soup
What do the following stand for?
- HTML, CSS, FTP, HTTP, DOM
- Ecma (trick question)
- CRUD
- DRY
- JSON
- CDN

### Other Concepts
- Separation of Concern
- Method Chaining
- Fluent Interfaces
- Subclass Sandbox
- Rendering Engine
- Display List


## III. Sample Questions (not exhaustive of what could be asked)

### CSS/HTML
1. Write a CSS rule that will select only those links on the page that have an `href` value of `http://www.google.com`

2. Write a CSS rule that will select all &lt;b> elements that are *children* of &lt;p> elements

3. Write a CSS rule that causes a link to turn green when the mouse is pressed down over it

4. Write a CSS rule that selects &lt;h1>, &lt;h2> and &lth3> tags and gives them a color of red

5. Re-write this HTML so that this &lt;p> element belongs to both the `hoser` and `takeoff` classes:

`<p><i>Strange Brew</i> is my favorite movie!</p>` 

### JavaScript & DOM
1. Write JS that selects **all** of the &lt;img> tags on a HTML page and stores them in an array, loops through the array, and gives each a `title` atttribute with the value of "I am an image"!"

1. Write JS that loops through the `colors` array, and creates an unordered list of the contents of the array. When you are done creating the arry, don't forget to add it to the page.

`let colors = ["red","green","blue"];`

### JS Objects

1. Create an ES6 *class* called `Person`. Its constructor will take two arguments `name` and `height`, and assign those passed in values as properties of the `Person object`. `Person` will have a `grow()` method that causes that instance's height to increase by 1.

1. Create a JS *object literal* named `rover` that has 2 properties `breed` and `age`. The object will also have a method named `getOlder()` which will increase age by 1.

### Other JS

1. What will be logged for this line of code? Why?

```js
if(""){
  console.log("Guns!");
}else{
  console.log("Butter!");
}
```

2. What will be logged for this line of code? Why?

```js
if([]){
  console.log("Guns!");
}else{
  console.log("Butter!");
}
```

3. What will be logged for this line of code? Why?

```js
if([].length){
  console.log("Guns!");
}else{
  console.log("Butter!");
}
```
