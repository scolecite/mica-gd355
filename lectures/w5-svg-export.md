# How to export to SVG
SVG is a vector file format just like AI or EPS, and you can open it in Illustrator and easily save as AI or PDF. p5.js is designed to work best within the browser and there is not yet a way to export to vector formats. We will rely on an external library to add this feature into our p5 sketches.

## Download library
Download [p5.SVG](https://github.com/zenozeng/p5.js-svg/).

## Set up your sketch.
From the downloaded library, find the file `p5.svg.js`. It can be found under `p5.js-svg-master` > `dist` folder. 

Copy the file into `libraries` folder of an empty p5 sketch.

## Adding the library
Open the empty sketch in Brackets editor. Open `index.html`. After the line, `<script language="javascript" type="text/javascript" src="sketch.js"></script>`, add a line like this:

```html
<script src="libraries/p5.svg.js"></script>
```

Save the file. Now, your sketch is ready to use the newly added library.

## Writing a sketch
Here, I will show you the basic structure you can use to export your sketch to SVG file. You can add your own code in the middle area.

```js
function setup() {
	createCanvas(400, 400, SVG); // add a third parameter, SVG.
}

function draw() {
	clear(); // this should be the first line of draw()
	
	/* add your own code below. */
	
	background(200);
	for (var i = 0; i < width; i+=10) {
		line(0, i, i, 0);
	}

}

// press s key to save SVG.
function keyTyped() {
	if (key === 's') {
		save();
	}
}
```

## Limitations
I have noticed that this method works for exporting a single static image, but does not work for storing the traces of multiple frames or real-time interactions with mouse position, etc. If you want a better SVG or PDF support, you should try [Processing](http://processing.org).

-----
You can download the example setup above [here](../../files/svg-export-template.zip).
