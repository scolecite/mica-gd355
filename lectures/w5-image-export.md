# How to export images
Let's take a look at a few different methods to export images from p5 sketches.

## Right-click
p5 sketches use HTML5 Canvas and you can simply right-click on the canvas and Save Image As...

## Save
Use these functions to save a single frame.

- [`save()`](http://p5js.org/reference/#/p5/save)
- [`saveCanvas()`](http://p5js.org/reference/#/p5/saveCanvas)

## Screenshot
You can always capture a simple screenshot. On Mac, press CMD + Shift + 4.

-----

## Video recording
`saveFrames()` in p5.js does not seem to be reliable. The best way to capture your work as a video is to use Quicktime Player's screen recording.

## Saving high resolution image
If you want to save an image that is larger than your screen, you can use the this technique. Say, you have this sketch:

```js
function setup() {
	createCanvas(200, 200);
	frameRate(20);
	background(200);
}

function draw() {	
	ellipse(0, 0, 100, 100);
	ellipse(width, 0, 100, 100);
	ellipse(0, height, 100, 100);
	ellipse(width, height, 100, 100);
	ellipse(width/2, height/2, 100, 100);
	textSize(96);
	text("a", 75, 125);
}
```

Now, you add `scaleFactor` variable, which will scale your canvas up or down. And you will use this variable anytime you are using width and height of the canvas. In the sketch below, you first need to scale your canvas by calling `createCanvas(200 * scaleFactor, 200 * scaleFactor);`. And inside `draw()`, add `scale(scaleFactor)` as the first line so that all the subsequent drawings will be scaled. Any numeric values will be automatically scaled, but for any expressions involving `width` or `height` will need to be scaled accordingly.

```js
var scaleFactor = 5;

function setup() {
	createCanvas(200 * scaleFactor, 200 * scaleFactor);
	frameRate(20);
	background(200);
}

function draw() {
	scale(scaleFactor);
	
	ellipse(0, 0, 100, 100);
	ellipse(width/scaleFactor, 0, 100, 100);
	ellipse(0, height/scaleFactor, 100, 100);
	ellipse(width/scaleFactor, height/scaleFactor, 100, 100);
	ellipse((width/scaleFactor)/2, (height/scaleFactor)/2, 100, 100);
	textSize(96);
	text("a", 75, 125);
}
```

-----

p5.js is best when used interactively within browsers. If you need to save images or video for other purposes, p5.js may not be the best option - you can try to convert into Processing sketch, which will provide many reliable options for exporting high resolution images, vector format graphics and image sequences.

