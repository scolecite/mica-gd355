# Main Structure

At the very minimum, your sketch should have two function blocks `setup()` and `draw()`. There are special functions that p5 uses.

```js
function setup() {
  createCanvas(400, 400); // create a canvas of 400 pixel width by 400 pixel height.
}

function draw() {

}
```

`setup()` will run *once* at the beginning, and then `draw()` will run continuously. For example, we only need to set the canvas size *once*, therefore, that code will go into the setup function. If you have any interactions that you need to track every frame, you do not want to put the code in the setup as it will only update once. Instead, put it inside the draw function.

Compare the two examples below:

```js
function setup() {
  createCanvas(400, 400); // create a canvas of 400 pixel width by 400 pixel height.
  ellipse(mouseX, mouseY, 100, 100);
}

function draw() {
}
```

```js
function setup() {
  createCanvas(400, 400); // create a canvas of 400 pixel width by 400 pixel height.
}

function draw() {
  ellipse(mouseX, mouseY, 100, 100);
}
```
