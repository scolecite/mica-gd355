# Transformation

The code above is good for placing the squiggles anywhere on screen, but what if we want to rotate them or scale them? We will have to use the matrix transformation.

Transformations such as position, rotation and scale works differently from what you are used to from Photoshop, Illustrator. In p5, when you want to move an object, for example, you cannot just move the object. You have to move the entire coordinate system. Although the languages are a little different, here is a great tutorial on [2D Transformations](https://processing.org/tutorials/transform2d/) on 


## Translate



## Rotate



## Scale



## Push and Pop



We will continue with the `drawSquiggle()` function we created in [the last posting](w4-function.md). Here is the code:

```js
function setup() {
	createCanvas(400, 400);
}

function draw() {
	background(220);
	
	drawSquiggle(10, 10);
	drawSquiggle(60, 120);
	drawSquiggle(210, 80);
	drawSquiggle(100, 180);
}

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
