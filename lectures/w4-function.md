# Function

## Draw a squiggle

Let's first draw a squiggle. `curveVertex()` is very useful for drawing free-flowing curves when you don't need precise controls. Just remember to repeat the first and last points twice.

```js
function setup() {
	createCanvas(400, 400);
}

function draw() {
	background(250);
	
	// draw squiggle
	strokeWeight(3);
	stroke(0);
	noFill();
	beginShape();
	curveVertex(50, 75);
	curveVertex(50, 75);
	curveVertex(75, 25);
	curveVertex(100, 75);
	curveVertex(125, 25);
	curveVertex(150, 75);
	curveVertex(175, 50);
	curveVertex(175, 50);
	endShape();
}
```

Drawing one squiggle may not be too difficult. But what if you want to draw ten? Do you want to add tens of lines of code each time? We can instead group the block of code with *a function*. Then, anytime you need to draw it, just call the function.

```js
function setup() {
	createCanvas(400, 400);
}

function draw() {
	background(250);
	
	drawSquiggle();
}

function drawSquiggle() {
	// draw squiggle
	strokeWeight(3);
	stroke(0);
	noFill();
	beginShape();
	curveVertex(50, 75);
	curveVertex(50, 75);
	curveVertex(75, 25);
	curveVertex(100, 75);
	curveVertex(125, 25);
	curveVertex(150, 75);
	curveVertex(175, 50);
	curveVertex(175, 50);
	endShape();
}
```

This is better in terms of the initial setup. Now, we don't need to look at the long code block. All we need to do is to call `drawSquiggle()` function anytime we want to draw it. But, this still does not solve our problem because if you call `drawSquiggle()` multiple times, they are all drawn on top of each other. We need to find a way to tell p5 *where* to draw each, so we can draw them anywhere we want.

## Multiple squiggles using parameters

What I eventually want to do is, when I call the function, I want to specify its location. So, instead of just calling it like:
```js
drawSquiggle();
```
I want to specify its x and y location like:
```js
drawSquiggle(20, 40);
```

Let's look at the function definition again.

```js
function drawSquiggle() {
	// draw squiggle
	strokeWeight(3);
	stroke(0);
	noFill();
	beginShape();
	curveVertex(50, 75);
	curveVertex(50, 75);
	curveVertex(75, 25);
	curveVertex(100, 75);
	curveVertex(125, 25);
	curveVertex(150, 75);
	curveVertex(175, 50);
	curveVertex(175, 50);
	endShape();
}
```

I will add two parameters to the function definition. I will call them `x` and `y`. The name of the parameters can be anything you choose. In this case `x` and `y` are most appropriate.

```js
function drawSquiggle(x, y) {
	// draw squiggle
	strokeWeight(3);
	stroke(0);
	noFill();
	beginShape();
	curveVertex(50, 75);
	curveVertex(50, 75);
	curveVertex(75, 25);
	curveVertex(100, 75);
	curveVertex(125, 25);
	curveVertex(150, 75);
	curveVertex(175, 50);
	curveVertex(175, 50);
	endShape();
}
```

We added the two parameters but we are not using them. Let's change our drawing code as below:

```js
function drawSquiggle(x, y) {
	// draw squiggle
	strokeWeight(3);
	stroke(0);
	noFill();
	beginShape();
	curveVertex(50 + x, 75 + y);
	curveVertex(50 + x, 75 + y);
	curveVertex(75 + x, 25 + y);
	curveVertex(100 + x, 75 + y);
	curveVertex(125 + x, 25 + y);
	curveVertex(150 + x, 75 + y);
	curveVertex(175 + x, 50 + y);
	curveVertex(175 + x, 50 + y);
	endShape();
}
```

It now does not matter what value we use for `x` and `y`. ALl the vertices will be offsetted accordingly. We can now go to `draw()` and call `drawSquiggle()` multiple times.

```js
function draw() {
	background(22);
	drawSquiggle(10, 10);
	drawSquiggle(60, 120);
	drawSquiggle(210, 80);
	drawSquiggle(100, 180);
}

```

Adding parameters means that you will have control over them. We now have control over the squiggle's position -- what else do you want to control? colors? line thickness? Try adding more parameters to the function definition.
