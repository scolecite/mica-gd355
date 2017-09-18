# Transformation

The code above is good for placing the squiggles anywhere on screen, but what if we want to rotate them or scale them? We will have to use the matrix transformation.

Transformations such as position, rotation and scale works differently from what you are used to from Photoshop, Illustrator. In p5, when you want to move an object, for example, you cannot just move the object. You have to move the entire coordinate system. Although the languages are a little different, here is a great tutorial on [2D Transformations](https://processing.org/tutorials/transform2d/) on 


## Translate
```js
translate(20, 20);
ellipse(0, 0, 20, 20);
```

```js
translate(20, 20);
ellipse(0, 0, 20, 20);

translate(40, 40);
ellipse(0, 0, 20, 20);
```

```js
pushMatrix();
translate(20, 20);
ellipse(0, 0, 20, 20);
popMatrix();

pushMatrix();
translate(40, 40);
ellipse(0, 0, 20, 20);
pushMatrix();
```

## Rotate
```js
ellipse(50, 0, 20, 20);

rotate(PI/8);
ellipse(50, 0, 20, 20);

rotate(PI/8);
ellipse(50, 0, 20, 20);
```

```js
background(255);
noFill();

rectMode(CENTER);
translate(width/2, height/2);
rect(0, 0, 60, 60);

rotate(PI/4);
rect(0, 0, 60, 60);
```

```js
void draw() {
  background(255);

  pushMatrix();
  translate(200, 100);
  rotate(frameCount/100.0); 
  translate(-70, -70); 
  bezier(37, 66, 16, 98, 53, 144, 72, 133);
  bezier(72, 133, 90, 121, 86, 103, 98, 80);
  bezier(98, 80, 111, 57, 140, 60, 121, 43);
  bezier(121, 43, 102, 27, 81, 22, 53, 22);
  bezier(53, 22, 24, 21, 52, 43, 37, 66);
  popMatrix();

  pushMatrix();
  translate(400, 100);
  rotate(-frameCount/10.0);
  translate(-185, -195);
  bezier(167, 193, 131, 190, 113, 189, 114, 216);
  bezier(114, 216, 114, 243, 160, 270, 185, 257);
  bezier(185, 257, 209, 244, 232, 222, 243, 193);
  bezier(243, 193, 254, 164, 215, 124, 198, 124);
  bezier(198, 124, 180, 125, 125, 109, 123, 128);
  bezier(123, 128, 121, 146, 184, 194, 167, 193);
  popMatrix();
}
```

```js
void draw() {
  background(255);

  // 원래 위치로 다시 이동시키는 대신에
  // 마우스의 현재위치만큼 이동하여 마우스를 따라다니게 한다.
  pushMatrix();
  translate(mouseX, mouseY);
  rotate(frameCount / 100.0);
  translate(-88, -84);

  bezier(60, 48, 71, 64, 9, 56, 17, 80);
  bezier(17, 80, 24, 104, 30, 121, 44, 121);
  bezier(44, 121, 58, 120, 68, 124, 68, 138);
  bezier(68, 138, 68, 152, 124, 156, 124, 136);
  bezier(124, 136, 124, 116, 130, 83, 141, 77);
  bezier(141, 77, 153, 70, 138, 42, 127, 40);
  bezier(127, 40, 116, 37, 95, 24, 92, 19);
  bezier(92, 19, 90, 15, 46, 26, 60, 48);
  popMatrix();
}
```

## Scale
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
