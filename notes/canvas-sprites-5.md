# 5 - JavaScript & the ES5 *Revealing Module Pattern*

## Overview
- In the last chapter we looked at how easy it is to utilize ES6 module syntax to create loosely coupled and highly maintainable code.
- The only issue with ES6 modules? They are supported only on recent versions of the major browsers.
- In this chapter, we will look at creating modular code using the *Revealing Module Pattern* - which is a popular technique for achieving modularity in pre-ES6 browsers. You can read about this pattern and others here: 
https://addyosmani.com/resources/essentialjsdesignpatterns/book/#revealingmodulepatternjavascript


## Contents
<!--- Local Navigation --->
I. [Back to ES5](#section1)

II. [The Revealing Module Pattern](#section2)

III. [Attaching modules to a global object](#section3)

<hr>

## I. <a id="section1">Back to ES5

Before we get started, grab the start files, which are based on the `Object.create()` demo from Chapter 2: [ES5-no-modules.zip](_files/ES5-no-modules.zip)

- Below is an external JS file that has some helpful code and variables in it. Some of this code we would like to keep public and visible elsewhere, some of it we want to hide away so it doesn't get mutuated or overwritten by code wriiten elsewhere.
- But under ES5, all of this code is in either Script scope or Global scope, and thus vulnerable to being overwritten by code written elsewhere (it could also overwrite other code itself)

**myutils.js** (For illustrative purposes only, don't create this file)
```javascript
"use strict";

// public stuff
let someVariable = 42;

function getRandomUnitVector(){
	let x = getRandom(-1,1);
	let y = getRandom(-1,1);
	let length = Math.sqrt(x*x + y*y);
	if(length == 0){ // very unlikely
		x=1; // point right
		y=0;
	} else{
		x /= length;
		y /= length;
	}

	return {x:x, y:y};
}

// stuff we would like to be private, but it's still public!
let privateVariable = 3.1415;
let secretCode = "ifmmp xpsme";

function getRandom(min, max) {
	return Math.random() * (max - min) + min;
}

// test it - everything is visible, everywhere!
console.log(revealingModule.someVariable); // 42
console.log(revealingModule.getRandomUnitVector); // function(){..}
console.log(revealingModule.getRandomUnitVector()); // something like {x:0.9722,y:0.2341}
console.log(revealingModule.privateVariable); // 3.1415
console.log(revealingModule.secretCode); // "ifmmp xpsme"
console.log(revealingModule.getRandom); // function(){..}
```

## II. <a id="section2">The Revealing Module Pattern
  
The ES5 Module pattern provides a way of creating a mix of public and private methods and variables, protecting the code from leaking into the global or script scope and accidentally colliding with code in other files. With this pattern, only a public API is returned, keeping everything else private.

- Below we define 3 variables and 2 functions inside of a function, and then call the function immediately (with the `()` at the end)
- Functions and variables defined within a function are local (private) to that function and not visible from the outside
- From this function, we will return one variable and one function reference that we want to expose (make public) to the rest of our program.
- This way of calling an anonymous function is know as an "Immediately Invoked Function Expression" aka IIFE or "Iffy"

**js/myutils-es5-module.js**
```javascript
"use strict";

let revealingModule = (function(){
	console.log("myutils-es5-module.js module loaded");
	
	// A) public stuff
	let someVariable = 42;

	function getRandomUnitVector(){
		let x = getRandom(-1,1);
		let y = getRandom(-1,1);
		let length = Math.sqrt(x*x + y*y);
		if(length == 0){ // very unlikely
			x=1; // point right
			y=0;
		} else{
			x /= length;
			y /= length;
		}

		return {x:x, y:y};
	}

	// B) private stuff
	let privateVariable = 3.1415;
	let secretCode = "ifmmp xpsme";

	function getRandom(min, max) {
		return Math.random() * (max - min) + min;
	}

// C) export a public interface to this module
		return{
			meaningOfLife: someVariable,
			getRandomUnitVector: getRandomUnitVector
		};
		
})(); // D) call the function immediately, which returns the interface above
```

Here's the code to try out our module - and verify that we have successfully hidden away some of the functions and variables.

**test-1.html**
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Test-1</title>
	<script src="js/myutils-es5-module.js"></script>
</head>
<body>

<script>
	console.log("** Page loaded **");
	// Test revealingModule - and we can only use what was returned from it
	console.log(revealingModule.meaningOfLife); // 42
	console.log(revealingModule.getRandomUnitVector); // function
	console.log(revealingModule.getRandomUnitVector()); // something like {x:0.9722,y:0.2341}
	console.log(revealingModule.someVariable); // undefined
	console.log(revealingModule.privateVariable); // undefined
	console.log(revealingModule.secretCode); // undefined
	console.log(revealingModule.getRandom); // undefined
</script>
</body>
</html>
```

When we load this in the browser, we can see the results:
- note that the module loads first, then the page
- only `meaningOfLife` and `getRandomUnitVector()` are visible, everything else is encapsulated and hidden from the outside - analagous to private members in languages like Java or C#

```javascript
myutils-es5-module.js module loaded
** Page loaded **
42
function(){....}
{x: 0.9152363302323804, y: -0.40291743549115044}
undefined
undefined
undefined
undefined
```

## III. <a id="section3">Attaching modules to a global object

A common way to create ES5 JS applications that have multiple modules is to create a single global object, and to make each module a property of that object.

Here is our new version of **myutils-es5-module.js** - note how we are now assigning the returned varaible and function to a property of an object named `app`:

```javascript
"use strict";

// 1)  If there is an `app` object already, use it.
// If `app` is nil, create an empty object literal
var app = app || {};

// 2) add a `utils` property to `app`
app.utils = (function(){
	console.log("myutils-es5-module.js module loaded");
	
	// A) public stuff
	let someVariable = 42;

	function getRandomUnitVector(){
		let x = getRandom(-1,1);
		let y = getRandom(-1,1);
		let length = Math.sqrt(x*x + y*y);
		if(length == 0){ // very unlikely
			x=1; // point right
			y=0;
		} else{
			x /= length;
			y /= length;
		}

		return {x:x, y:y};
	}

	// B) private stuff
	let privateVariable = 3.1415;
	let secretCode = "ifmmp xpsme";

	function getRandom(min, max) {
		return Math.random() * (max - min) + min;
	}

// C) export a public interface to this module
	return{
		meaningOfLife: someVariable,
		getRandomUnitVector: getRandomUnitVector
	};
		
})(); // D) call the function immediately, which returns the interface above

```

- We can now call the `getRandomUnitVector()` function like this:
    - `app.utils.getRandomUnitVector()`
    - and access `someVariable` like this - `app.utils.meaningOfLife`

Here is a new module named **test.html**:
	
<hr><hr>

**[Previous Chapter <- JavaScript & ES6 Modules (chapter 4)](canvas-sprites-4.md)**
