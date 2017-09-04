# Type Functions
There are several type related function in p5.js and you can find the list [here](http://p5js.org/reference#group-Typography). Let's take a look at them.

## Writing text
You write text on screen with `text()` function.
```js
text("hello world!", 10, 50);
```
Your message must be placed within the double quote block `" "`. We call it *a string*. The second and third parameters are the x and y positions. There are the optional fourth and fifth parameters if you want to set up a text box. Look at [this example](http://p5js.org/reference/#/p5/text).

## Text size
```js
textSize(24);
text("Type", 20, 50);
```

## Font
You can set the font to what you want. You have to have the font installed on your computer. How to find the right name to use? Open up the Font Book app (on Mac), and copy the PostScript name of the font. If you share your project online, make sure that your audience also has the same font on their machines. This is hard to guarantee in most cases, so it might be a good idea to use one of the web safe fonts.
```js
textFont("Roboto-BlackItalic");
textSize(128);
text("Any font", 20, 150);
```
An alternative way is to store OTF or TTF files in your p5.js sketch folder and load. Look at [this exmaple](http://p5js.org/reference/#/p5/textFont).

## Text align
The default value is `textAlign(LEFT, BASELINE);`.

http://p5js.org/reference/#/p5/textAlign

## Text leading
http://p5js.org/reference/#/p5/textLeading

## Text width
`textWidth()` function is *not* for setting the text width. It instead *returns* you the width of the text you give to the function. This is useful to find the current position of the (imaginary) cursor.

http://p5js.org/reference/#/p5/textWidth

```js
  textFont("Roboto-Black")
  textSize(64);
  
  var s = "Typography";
  var x = 20;
  var y = 150;
  for (var i = 0; i < s.length; i++) {
    var w = textWidth(s[i]);
    stroke(0);
    fill(255);
    rect(x, y-64, w, 64);
    noStroke();
    fill(255, 0, 0);
    text(s[i], x, y);
    x += w;
  }
```

## Keyboard input
The most recently typed key is stored in `key` variable.
```js
var s = "";

function setup() {
  createCanvas(500, 500);
  background(255);
  textSize(128);
}

function draw() {
  stroke(255);
  fill(0);
  text(s, mouseX, mouseY);
}

function keyTyped() {
  s = key;
  
  if (key == ' ') {
    background(255);
  }
}
```

## Loading webfonts
Instead of relying on the system fonts, you can load in web fonts just like you would with HTML/CSS. Let's find a font on [Google FONTS](https://fonts.google.com). For example, I found [Merriweather fonts](https://fonts.google.com/specimen/Merriweather) on Google Fonts. You need to get the link code that looks like this:

  `<link href="https://fonts.googleapis.com/css?family=Merriweather" rel="stylesheet">`

Then, include the line inside the head of your `index.html` file of your p5 sketch like this:
  ```html
  <head>
    <meta charset="UTF-8">
    <script language="javascript" type="text/javascript" src="libraries/p5.js"></script>
    <script language="javascript" type="text/javascript" src="sketch.js"></script>
    <link href="https://fonts.googleapis.com/css?family=Merriweather" rel="stylesheet">
  </head>
  ```
All you need to do now is the set the `textFont()` to that you just included.
```js
textFont('Merriweather');
text("It works!", 100, 100);
```

## *Exercise*
*Now you know the several functions related to typography. You also know how to use many other basic drawing functions. Combine those and explore the letterform-making through code. Tips: Use `mouseX` and `mouseY` instead of numbers for interactions. Look at [this example](http://codepen.io/cdaein/pen/wgdORj).*
