# 6 - Transpiling ES6 to ES5

## Overview



## Contents
<!--- Local Navigation --->
I. [What is *transpiling*?](#section1)

II. [Babel](#section2)

III. [NPM & webpack](#section3)

IV. [Transpiling an ES6 project down to ES5](#section4)

<hr>

## I. <a id="section1">What is *transpiling*
  
https://scotch.io/tutorials/javascript-transpilers-what-they-are-why-we-need-them

## II. <a id="section2">Babel
  
- https://babeljs.io
- https://www.npmjs.com/package/browserify

## III. <a id="section3">NPM & webpack
  

## IV. <a id="section4">Transpiling an ES6 project down to ES5
	
- Go get your *canvas-sprites-4-HW.html* code - this is the one that uses ES6 classes and ES6 modules
- We are going to transpile all of that ES6 code to ES5 so that it will run on all recent browsers, even ones that don't know about ES6
  
 **1) Install Node.js and the Node Package Manager (npm)**
 
 You could do this with nvm (the Node Version Manager) like this:
 
 `curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash`
 
 and then: 
 
 ```js
 nvm install node
 nvm -v
 npm install npm@latest -g`
 ```
 
 Or you can head to https://nodejs.org/en/download/ and grab an installer - instructions are here:
 
 https://docs.npmjs.com/getting-started/installing-node
 
 Once Node.js is installed, head to the command prompt to install npm:
 
 ```js
 npm -v
 npm install npm@latest -g
 ```
 
 **Note: Mac OS users will often have to have `sudo` at the beginning of the command whenever they are installing applications or packages.**
 
 **2) Change directory to your project folder**
 
 ![Screenshot](transpiling-1.jpg)
 
 **3) Verify that the node and npm versions are up-to-date**
 
 ```js
 node -v
 npm -v
 ```
 
 **4) Create a node project with npm**
 
 ```js
 npm init -y
 ```
 
 Which will create your **package.json** file with defaults settings, which are in an object literal, with should look something like this:
 
 ```js
 {
  "name": "part-IV-homework",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
 ```
  
**5) Next we need to install webpack**

```js
npm install webpack --save
```
- Which will download all of the modules you will need - check out the `node_modules` folder in your project directory
- This will also add a `"dependencies"` key to *package.json*


```js
"dependencies": {
    "webpack": "^3.11.0"
}
```
  


**Mac users will probably need `sudo` again**

**6) Create *webpack.config.js***

**webpack.config.js**
```js
module.exports = {
    entry: ['./js/init.js','./js/classes.js','./js/main.js','./js/utilities.js'],
    output: {
        filename: './dist/bundle.js'
    }
};
```

- You can see above that `module.exports` is an object literal:
    - `entry` contains an array of all of the JS files we wish to compile
    - `output` is the name of the single file we will compile to
    
**7) Modify *package.json***

Open up *package.json* and make the "scripts" key look like this:

```js
"scripts": {        
    "start": "npm run webpack",
    "webpack": "webpack -d --watch"
},
```

**8) Run npm!**

```js
npm start
```
This executes `webpack -d --watch` for you.

You should now see that *dist/bundle.js* has been created. If you open *bundle.js*, you will see that your 4 JavaScript files have been compiled to ES5 and the results placed in it.

**9) Edit your HTML file**

Make your HTML file look like this:

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Canvas & ES6 Classes - HW</title>
</head>
<body>
	<canvas width="600" height="400"></canvas>
<!-- 	<script src="js/init.js" type="module"></script> -->
	<script src="dist/bundle.js"></script>
</body>
</html>
```

- we are now pointing the &lt;script> tag at the compiled JS file at *dist/bundle.js* rather than at *init.js*
- note that this is a regular ES5 JavaScript file now, so we don't need `type="module"` any longer


**10) Final Test**
- Reload the page, everthing should work as before!
- Note that webpack is stil running and watching our files, and if we make any chnages, it will recompile our fiels for us automatically

**11) Distribution**
When you post this to the web:
- you need the HTML file, *dist/bundle.js*, and your *images* folder
- you don't need your `js` folder - becasue all that ES6 has been compiled down to ES5 and put into *bundle.js*
- you don't need any of the other of the other configuration files or packages



<hr><hr>

**[Previous Chapter <- JavaScript & the ES5 *Revealing Module Pattern* (chapter 5)](canvas-sprites-5.md)**
