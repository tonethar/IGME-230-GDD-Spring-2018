# 1 - Intro to Canvas Sprites

## Overview
Let's get stuff moving on the screen, and explore the many techniques we have for creating objects in JavaScript.


## Contents
<!--- Local Navigation --->
I. [A Bouncing Circle!](#section1)


<hr>

## <a id="section1">I. A Bouncing Circle!

To get things going, you are actually going to have to create 4 files - but it will be worth it because we will be reusing these files throughout this entire series.

**canvas-sprites-intro-1.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Intro to Canvas Sprites</title>
</head>
<body>
<canvas width="600" height="400"></canvas>
	<script src="js/utilities.js"></script>
	<script src="js/classes.js"></script>
	<script src="js/main.js"></script>
</body>
</html>
```

**js/utilities.js**

```javascript
function getRandomUnitVector(){
	let x = getRandom(-1,1);
	let y = getRandom(-1,1);
	let length = Math.sqrt(x*x + y*y);
	if(length == 0){ // very unlikely
		x=1; // point right
		y=0;
		length = 1;
	} else{
		x /= length;
		y /= length;
	}

	return {x:x, y:y};
}

function getRandom(min, max) {
	return Math.random() * (max - min) + min;
}
```

**js/classes.js**
```javascript
// empty for now
```

**js/main.js**
```javascript
// these variables are in "Script scope" and will be available in this and other .js files
const ctx = document.querySelector("canvas").getContext("2d");
const screenWidth = 600;
const screenHeight = 400;

let color = "red";
let radius = 20;
let x = Math.random() * (screenWidth - 100) + 50;
let y = Math.random() * (screenHeight - 100) + 50;
let fwd = getRandomUnitVector();
let speed = 2;

loop();


function loop(){
	// schedule a call to loop() in 1/60th of a second
	requestAnimationFrame(loop);
	
	// move circle
	x += fwd.x * speed;
	y += fwd.y * speed;
		
	// check sides and bounce
	if (x <= radius || x >= screenWidth-radius){
			fwd.x *= -1; 
	}
	
	if (y <= radius || y >= screenHeight-radius){
		fwd.y *= -1; 
	}
	
	// draw background
	ctx.fillRect(0,0,screenWidth,screenHeight)
	
	// draw circle
	ctx.save();
	ctx.beginPath();
	ctx.arc(x, y, radius, 0, Math.PI*2, false);
	ctx.closePath();
	ctx.fillStyle = color;
	ctx.fill();
	ctx.restore();
}
```

**Which gives us the following:**

![Screenshot](_images/canvas-sprites-intro-1.jpg)


## <a id="section2">II. Creating an Object Literal

**Note: If you need a refresher on JavaScript object literals, please read this tutorial page: [JavaScript Object Literals](web-apps-7.md)**

We are now going to simplify our code somewhat by moving most of the circle moving and drawing code onto a single object literal.





### VIII. <a id="section8">Nota Bene
Nothing for now.

### IX. <a id="section9">Review Questions



### X. <a id="section10">Review Exercise


<hr><hr>

**[Table of Contents <- About this Canvas Sprites Tutorial Series](canvas-sprites-0.md)**
  
