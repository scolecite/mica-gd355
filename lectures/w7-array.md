# Arrays 

*An array is a list of data. Each piece of data in an array is identified by an index number representing its position in the array. Arrays are zero based, which means that the first element in the array is [0], the second element is [1], and so on. - from [p5js.org](https://p5js.org/examples/arrays-array.html)*

## Visualize walking data 

Say, you are tracking the number of steps you've walked every day. You would create a variable for each day:

```js
var mar01 = 3021;
var mar02 = 3512;
var mar03 = 1334;
var mar04 = 5119;
```

You see how tedious it can be to create and manage multiple variables like this. Instead, we can use an *array* to group the variables together:

```js
var march= []; // create an empty array
marchSteps[0] = 3021; // assign values
marchSteps[1] = 3512;
marchSteps[2] = 1334;
marchSteps[3] = 5119;
```

Or, we can do this all in one line:

```js
var marchSteps = [3021, 3512, 1334, 5119];
```

When we need to access the March 1st step count, we can use the array index as `marchSteps[0]`. Note that the counting starts at *zero*.

```js
// to see the March 1st step count
console.log(marchSteps[0]);
```

Later, if you want to add more data to the array, we will *push* it into the array. The data that gets pushed is added at the end of your array:

```js
var marchSteps = [3021, 3512, 1334, 5119];
marchSteps.push( 4211 ); // March 5th step count.

console.log(marchSteps[4]);
```

If you want to check the current length of the array:

```js
console.log( marchSteps.length );
```

If you want to delete an element from the array, use `splice()`:

```js
var myArray = [10, 11, 12, 13, 14, 15, 16, 17, 18, 19]; 
console.log(myArray); // before
myArray.splice(0, 3);
console.log(myArray); // after
```

Because an array holds many elements, you normally use arrays and for loops together. Let's put together everything we've learned so far to visualize our walking data:

```js
var marchSteps = [3543, 2459, 2042, 866, 1220, 5434, 7112, 33, 11, 418, 5729, 2737, 1406, 4839];

function setup() {
	createCanvas(800, 500);
}

function draw() {
  background(200);
	
	for (var i = 0; i < marchSteps.length; i++) {
		var h = map(marchSteps[i], 0, 10000, 0, 400);
		rect(i*50, height-100, 40, -h);
		text(marchSteps[i], i*50, height-80);
	}
}
```
