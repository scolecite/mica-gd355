# Annyang basic example

Add the line below to `<head>` in `index.html` first.

```js
<script src="//cdnjs.cloudflare.com/ajax/libs/annyang/2.6.0/annyang.min.js"></script>
```

```js
var sceneNum = 0;
var bgCol = 'white';

var commands = {
	'set the background :name': function(name) {
		bgCol = name;
	},
	'안녕 :name': function(name) {
		console.log(name);
	},
	'next': function() {
		sceneNum++;
	},
	'previous': function() {
		sceneNum--;
	}
};

function setup() {
	createCanvas(500, 500);
	
//	annyang.setLanguage('ko');
	annyang.addCommands(commands);
	annyang.start();
}

function draw() {
	background(bgCol);
	
	if (sceneNum == 0) {
		line(0, 0, width, height);
	} else if (sceneNum == 1) {
		ellipse(width/2, height/2, 200, 200);
	} else if (sceneNum == 2) {
		background(255, 255, 0);
	}
}


```
