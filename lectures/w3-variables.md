# Variables

## System Variables

### Mouse position
`mouseX` and `mouseY` store the current mouse position in numbers.

```js
function draw() {
  ellipse(mouseX, mouseY, 100, 100);
}
```

```js
function draw() {
  fill(mouseX, 0, 255);
  ellipse(mouseX, mouseY, 200, 200);
}
```

### Previous mouse position
`pmouseX` and `pmouseY` store the mouse position of the previous frame.

```js
function draw() {
 line(pmouseX, pmouseY, mouseX, mouseY);
}
```

### Canvas width and height
`width` and `height` variables store the width and height of the current canvas.

```js
function setup() {
  createCanvas(500, 500);
}

function draw() {
  background(200);
  ellipse(width/2, height/2, 200, 200);
  line(0, 0, width, height);
  line(width, 0, 0, height);
}
```

### Window size
`windowWidth` and `windowHeight` store the size of the browser window. As you resize the window, the values will change.

```js
function setup() {
  createCanvas(windowWidth, windowHeight);
}

function draw() {
  background(200);
  ellipse(width/2, height/2, 200, 200);
}

function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
}
```

### Counting frames
`frameCount` stores the number of frames that have passed since the sketch started running. As the sketch keeps running, the value will keep increasing.

```js
function draw() {
  console.log(frameCount);
}
```

## Create your own variable
A variable stores a value in the computer memory so that it can be used later in a program. Once you create a variable, you can use it as many times as you want. The value can also be changed while the program is running.

```js
var life = 3; // declare and initialize a variable
```

When creating a variable, use a descriptive name.
```js
var a = 21; // what is a?
var age = 21; // this is better.
```

Variables are not limited to a number. You can store more complex data in a variable. Below is an example of color.
```js
var col = color(0, 200, 100);
fill(col);
ellipse(width/2, height/2, 100, 100);
```

### Variable scope
When a variable is declared outside of any functions such as `setup()` or `draw()`, it can be used from anywhere in the program. This is called a *global variable*.
```js
var diam = 200; // global variable

function setup() {
  createCanvas(400, 400);
}

function draw() {
  ellipse(width/2, height/2, diam, diam);
}
```

When a variable is declared within a function, it can only be used within the function it was created from. This is called a *local variable*.

```js
function setup() {
  createCanvas(400, 400);
  var diam = 200; // local variable
}

function draw() {
  ellipse(width/2, height/2, diam, diam); // error - draw() cannot see diam variable.
}
```
  
## Print to console
To print a value, use `console.log()`. This is useful to check the current value of any variables.

```js
var a = "How are you?"
console.log(a);

var b = 3;
console.log(b);
```

What you print using `console.log()` does not show up on your canvas. You have to open up the JavasScript console from the browser.


## Assignment operator
One equal sign `=` is an assignment operator. It does not mean that the values on the left and right side of the equation are the same. To evaluate, you need to use either two equals `==` or three equals `===`.

```js
var a = 10;
var b = a;
console.log(b);

var c = 10;
var d = 15;
d = c;
console.log(d);

var e = 10;
e = e + 5;
console.log(e);

var f = 12;
f = f * 2;
console.log(f);
```
  
-----
*Exercise: Draw multiple shapes on screen. Set their properties such as x, y coordinates, size, color, etc. Now, create a variable (or use one of the existing system variables) and apply the same variable to multiple shapes. Change the value and see how they relate.*
