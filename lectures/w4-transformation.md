# Transformation

Transformations such as position, rotation and scale works differently from what you are used to from Photoshop, Illustrator. In p5, when you want to move an object, for example, you cannot just move the object. You have to move the entire coordinate system. Although the languages are a little different, here is a great tutorial on [2D Transformations](https://processing.org/tutorials/transform2d/) for [Processing](http://processing.org).


## Translate

When you translate, you translate the entire coordinate system, not a single object. This is where it can get confusing. Think of a drawing on paper - you are moving the entire paper around, not the drawing itself.

```js
translate(20, 20);
ellipse(0, 0, 20, 20);
```
In the example above, the ellipse is drawn at the origin. It's just that the origin has now moved to `(20, 20)` because `translate(20, 20)`.

### Accumulation
```js
translate(20, 20);
ellipse(0, 0, 20, 20);

translate(40, 40);
ellipse(0, 0, 20, 20);
```
The translation affects everything that's drawn after it, and the effect accumulates. Although the two ellipses use the same coordinates, they are drawn at different location because of the translations.

### Control individual shapes
```js
push();
translate(20, 20);
ellipse(0, 0, 20, 20);
pop();

push();
translate(40, 40);
ellipse(0, 0, 20, 20);
pop();
```
If you want to have more control over translation, anytime you translate, create `push()` and `pop()` blocks to enclose the shapes you want to translate. Only the codes within the push/pop block will be affected.

## Rotate

Rotation works similarly to translation. p5js can only rotate the coordinate system from its origin `(0, 0)`. 

```js
rect(50, 0, 20, 20);

rotate(PI/8);
rect(50, 0, 20, 20);

rotate(PI/8);
rect(50, 0, 20, 20);
```

Also, keep in mind that the parameter `rotate()` function takes is in radians, not degrees. For example, if you want to rotate by 90 degrees, you will write `rotate(PI/2)`. If the radians are confusing to you, you can first convert to the degrees before rotating as in `rotate( degrees(PI/2) )`. It will do the conversion for you.

### Rotate from center of shape

p5.js can only rotate from the origin `(0, 0)`, so it requires a little bit of thinking to rotate shapes from their own center. First, think about where to place the shape, and then, translate by that much. Draw the shape at the origin `(0, 0)` as that's the only coordinate that p5 canvas can be rotated from.

```js
background(255);
noFill();

rectMode(CENTER);
translate(width/2, height/2); // this is where rect will be drawn
rect(0, 0, 60, 60); // draw at the origin

rotate(PI/4); // rotate the coordinate system
rect(0, 0, 60, 60); // draw at the origin
```

If you have a complex shape, you will first need to determine what point you want to use as its center. It helps to first draw shapes in Illustrator using the Info panel, that way, you will know the exact coordinates.

```js
function draw() {
  background(255);
	noFill();

  push();
  translate(100, 100);
  rotate(frameCount/100.0); 
  translate(-70, -70); 
	beginShape();
	vertex(37, 66);
	bezierVertex(16, 98, 53, 144, 72, 133);
	bezierVertex(90, 121, 86, 103, 98, 80);
	bezierVertex(111, 57, 140, 60, 121, 43);
	bezierVertex(102, 27, 81, 22, 53, 22);
	bezierVertex(24, 21, 52, 43, 37, 66);
	endShape();
  pop();

  push();
  translate(200, 100);
  rotate(-frameCount/10.0);
  translate(-185, -195);
	beginShape();
	vertex(167, 193);
	bezierVertex(131, 190, 113, 189, 114, 216);
	bezierVertex(114, 243, 160, 270, 185, 257);
	bezierVertex(209, 244, 232, 222, 243, 193);
	bezierVertex(254, 164, 215, 124, 198, 124);
	bezierVertex(180, 125, 125, 109, 123, 128);
	bezierVertex(121, 146, 184, 194, 167, 193);
	endShape();
  pop();
}
```


### Follow the mouse while rotating

```js
function draw() {
	background(255);

	push();
	translate(mouseX, mouseY);
	rotate(frameCount / 100.0);
	translate(-88, -84);

	beginShape();
	vertex(60, 48);
	bezierVertex(71, 64, 9, 56, 17, 80);
	bezierVertex(24, 104, 30, 121, 44, 121);
	bezierVertex(58, 120, 68, 124, 68, 138);
	bezierVertex(68, 152, 124, 156, 124, 136);
	bezierVertex(124, 116, 130, 83, 141, 77);
	bezierVertex(153, 70, 138, 42, 127, 40);
	bezierVertex(116, 37, 95, 24, 92, 19);
	bezierVertex(90, 15, 46, 26, 60, 48);
	endShape();

	pop();
}
```

## Scale

Scaling works the same way from the origin `(0, 0)`. So, if you want to scale from the center, then, you will first need to translate by that much. Also, notice that the stroke weight gets scaled.

```js
background(255);
noFill();

translate(width/2, height/2);
ellipse(0, 0, 50, 50);

for (int i = 0; i < 12; i++) {
  scale(1.2);
  ellipse(0, 0, 50, 50);
}
```


## Example


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
