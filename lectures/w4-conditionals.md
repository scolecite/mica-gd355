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

