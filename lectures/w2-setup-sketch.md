
# Setting up a p5.js sketch
different ways to setup a p5.js sketch.

### Brackets
1. First, download the p5.js complete library from http://p5js.org
1. Unzip the file.
1. Inside the folder, you will see `empty-example` folder.
1. Make a copy of this `empty-example` folder and rename it to what you want, say, `my-first-sketch`. Do not rename anything inside - `index.html`, `libraries` or `sketch.js`.
1. Drag the folder and drop it onto the Brackets code editor.
1. Now, you can live preview the `index.html`.
1. Add your own code in `sketch.js`.
1. Anytime you save, the live preview will update.
1. If the live preview does not work, close the browser window and try again.


### Codepen
1. Create a new pen.
1. Click the gear icon next to JS tab.
1. Under Add External JavaScript, copy and paste the following:
  `https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.5.6/p5.min.js`
1. Save & Close.
1. Now, start coding in the JS tab. (You don't need anything in HTML or CSS tab.)

### OpenProcessing
[OpenProcessing](https://www.openprocessing.org) does not need any setup. Just create a sketch and have fun.

## Main Structure
At the very minimum, your sketch should have two function blocks `setup()` and `draw()`. Define the size of the canvas with `createCanvas()` function.
```js
function setup() {
  createCanvas(400, 400); // create a canvas of 400 pixel width by 400 pixel height.
}

function draw() {

}
```



