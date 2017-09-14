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

Drawing one squiggle may not be too difficult. But what if you want to draw ten? Do you want to add tens of lines of code each time? We can instead group the block of code with *a function*.

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

This is better in terms of the initial setup. Now, we don't need to look at the long code block. All we need to do is to call `drawSquiggle()` function anytime we want to draw it. But, this still does not solve our problem because if you call `drawSquiggle()` multiple times, they are all drawn on top of each other. We need to find a way to tell p5 *where* to draw each.

## Multiple squiggles

