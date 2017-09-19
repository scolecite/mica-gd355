# Conditionals

Let me introduce a new system variable `mouseIsPressed`. This is a variable that will return `true` if the mouse is pressed and `false` if the mouse is not pressed. This type of variables are called boolean variables. It has only two states - `true` or `false`. Now, we can make part of our program run only when the condition is met.

```js
function setup() {
	createCanvas(400, 400);
	background(220);
}

function draw() {
	if (mouseIsPressed) {
		fill(0, 255, 255);
		ellipse(mouseX, mouseY, 50, 50);
	}
}
```

What the code above does is *if* mouse is currently pressed, run the code between `{` and `}`.

This is different from `mousePressed()` function. Compare the result:

```js
function setup() {
	createCanvas(400, 400);
	background(220);
}

function draw() {
}

function mousePressed() {
	fill(255, 255, 0);
	ellipse(mouseX, mouseY, 50, 50);
}
```

With `mousePressed()` function, you cannot drag and create brush marks because it will only run once the mouse is pressed unlike `mouseIsPressed`, which will keep tracking the mouse state every frame.

### Combine mouseIsPressed and mousePressed()

We can combine both `mousePressed()` function and `mouseIsPressed` boolean variable in the same program.

```js
function setup() {
	  createCanvas(400, 400);
	  background(255);
	  noFill();
}

function draw() {
 	stroke(200);
	if (mouseIsPressed) {
		ellipse(mouseX, mouseY, 20, 20);
	}
}

function mousePressed() {
	background(255);
}
```


### What about a key press?

We can check the key presses, too!

```js
function setup() {
  createCanvas(400, 400);
  background(255);
  noFill();
}

function draw() {
	background(220);
	
	if (keyIsPressed) {
		background(120, 200, 0);
	}
}
```

### Which key?

We can check the multiple conditions with logical AND `&&`. This will return true only if the two conditions are met. There is also logical OR `||`.

```js
function setup() {
  createCanvas(400, 400);
  background(255);
  noFill();
}

function draw() {
	background(220);
	
	if (keyIsPressed && key == 'a') {
		background(120, 200, 0);
	}
}
```

### Nesting if statements

If you want to map multiple keys, nested if statements might be a better option.

```js
function setup() {
  createCanvas(400, 400);
  background(255);
  noFill();
}

function draw() {
	background(220);
	
	if (keyIsPressed) {
		if (key == 'a') {
			background(120, 200, 0);
		} else if (key == 's') {
			background(0, 200, 200);
		} else if (key == 'd') {
			background(200, 0, 150);
		} else if (key == 'f') {
			background(120, 200, 250);
		}
	}
}
```

## Create your own boolean variable

```js

```


## Further learning
- [Processing interactivity tutorial](https://processing.org/tutorials/interactivity/)
- [p5.js interactivity example](https://p5js.org/examples/hello-p5-interactivity-1.html)


