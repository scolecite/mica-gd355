# Advanced Drawing
We will take a look at more advanced drawing functions in this section.

## Counter shape
```js
noStroke();
fill(0);
beginShape();
vertex(250, 0);
vertex(500, 500);
vertex(400, 500);
vertex(350, 400);
vertex(150, 400);
vertex(100, 500);
vertex(0, 500);

beginContour();
vertex(250, 200);
vertex(200, 300);
vertex(300, 300);
endContour();

endShape(CLOSE);
```
Notice that if you draw a main shape clockwise, then your contour *must* be drawn counter-clockwise. Look at [this example](http://codepen.io/cdaein/pen/JENxOm).

*Exercise: Draw a shape that has a counter.*

## Arc
You can draw part of an ellipse or arc. `arc()` function needs quite a few parameters.
```js
arc(centerX, centerY, width, height, startAngle, endAngle);
```
By default, p5.js uses *radians* to measure angles. The radian measurements are based on &pi; (pi), the ratio of a circle's circumference to its diameter. &pi; is approximately 3.141592. 0 degree is equal to 0 radians, and 180 degree is equal to 2&pi; radians. See [this animation](https://en.wikipedia.org/wiki/File:Circle_radians.gif). So, if you want to draw a quarter (90 degree) circle, you will say:
```js
arc(width/2, height/2, 100, 100, 0, PI/2);
```
If the radians sound too confusing, you can use degrees (from 0 to 360, instead of 0 to 2&pi;) by using `radians()` function. This function will convert degrees to more machine-friendly radians. The code above can be expressed this way:
```js
arc(width/2, height/2, 100, 100, 0, radians(90));
```
If you want to only use degrees for your entire sketch, then place this line somewhere in `setup()`:
```js
angleMode(DEGREES);
```
Note that most code examples you find will use radians, so it's a good idea to get used to the radians measurement.

*Exercise: Draw a pie chart that visualizes your day by hour. Use different colors for different activities - sleep, commute, class, work, etc.*

## Curves
Drawing curves in p5.js is not easy. There are mainly two different curve types - curve and bezier.

### Curve
To see how a curve works, look at [this interactive example](http://codepen.io/cdaein/pen/pRPLYY). You would probably not use `curve()` function on its own. When you use a series of `curveVertex()`, you can create a smooth curvy line.

### Bezier
A bezier curve is what you create with the pen tool in Adobe Illustrator. 

It takes two points and two control points when you draw a single bezier curve.
```js
bezier(x1, y1, cx1, cy1, cx2, cy2, x2, y2);
```
If you want to continue drawing and connecting multiple bezier curves, use `beginShape()` and `endShape()`:
```js
beginShape();
vertex(30, 70); // first point
bezierVertex(25, 25, 100, 50, 50, 100);
bezierVertex(20, 130, 75, 140, 120, 120);
endShape();
```

### More?
Processing has [a great tutorial](https://processing.org/tutorials/curves/) on how to work with curves. Although the syntax is a little different from p5.js, you should be able to follow along.
