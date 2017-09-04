# Advanced Drawing
We will take a look at more advanced drawing functions in this section.

## Counter shape
Some letters have a hole in it, such as O, P, R, etc. You can use contour functions to handle it.
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
Notice that if you draw a main shape clockwise, then your contour should be drawn counter-clockwise. Look at [this example](http://codepen.io/cdaein/pen/JENxOm).

*Exercise: Draw a letter that has a counter.*

## Arc
You can draw part of an ellipse or arc. `arc()` function needs quite a few parameters.
```js
arc(centerX, centerY, width, height, startAngle, endAngle);
```
By default, p5.js uses radians to measure angles. The radian measurements are based on &pi; (pi), the ratio of a circle's circumference to its diameter. &pi; is approximately 3.141592. 0 degree is equal to 0 radians, and 180 degree is equal to 2&pi; radians. See [this animation](https://en.wikipedia.org/wiki/File:Circle_radians.gif). So, if you want to draw a quarter (90 degree) circle, you will say:
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

*Exercise: See if you can create a few letters from Peter Cho's [Type Me, Type Me Not](http://www.typotopo.com/projects.php?id=typemenot). The whole typeface uses 2 arcs for each letter.*

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

### Convert from Illustrator to p5.js code
If drawing curves by plotting points look difficult, you can create shapes in other programs such as Illustrator, then translate the shapes to p5.js codes. There is no simple way to do this in p5.js yet, but, if you follow a few extra steps, you can replicate your Illustrator paths in p5.js.

  1. Draw a path in Illustrator.
  1. Save as, and choose SVG as file format.
  1. In the save dialog, click on SVG Code.
  1. Copy the SVG code. All we need is a line that starts with `<path class=...`.
  1. Visit this link: http://www.professorcloud.com/svg-to-canvas/
  1. Paste the SVG code in the text box.
  1. Click convert.
  1. Copy the generated code.
  1. This is a html5 canvas code, which is different from p5.js JavaScript code.
  1. replace any `moveTo()` or `lineTo()` with `vertex()`. 
  1. replace any `bezierCurveTo()` with `bezierVertex()`.
  1. round the numbers to integers.
  1. surround the code with `beginShape()` and `endShape()`.
  1. It should work now!

### More?
Processing has [a great tutorial](https://processing.org/tutorials/curves/) on how to work with curves. Although the syntax is a little different from p5.js, you should be able to follow along.
