# Transformation

Transformations such as position, rotation and scale works differently from what you are used to from Photoshop, Illustrator. When you want to move an object, for example, you cannot just move the object. You are, in fact, moving the entire coordinate system.

## Draw a squiggly

```js
function setup() {
	createCanvas(400, 400);
}

function draw() {
	background(250);
	
	// draw squiggly
	strokeWeight(3);
	stroke(0);
	noFill();
	beginShape();
	curveVertex(50, 50);
	curveVertex(50, 50);
	curveVertex(75, 25);
	curveVertex(100, 75);
	curveVertex(125, 25);
	curveVertex(150, 75);
	curveVertex(175, 50);
	curveVertex(175, 50);
	endShape();
}
```


## Translate


## Rotate


## Scale


## Push and Pop
