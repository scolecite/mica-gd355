# Arithmetic

## Addition
```js
console.log( 3 + 4 );
console.log( 123 + 456 );
```

### Concatenation
```js
var a = "hello";
var b = "world";
console.log( a + b );
```

## Subtraction
```js
console.log( 12 - 5 );
console.log( 1 - 80 );
```

## Multiplication
```js
console.log( 8 * 8 );
console.log( 100 * 0.1 );
```

## Division
```js
console.log( 12 / 4 );
console.log( 1 / 3 );
```

## The order of operations
```js
console.log( 1 + 2 * 3 );
console.log( (1 + 2) * 3 );
```

## Modulus
When you use modulus operator `%`, It will return you the remainder from the division.
```js
console.log( 12 % 4 ); // 0
console.log( 12 % 5 ); // 2
```

## Ceil
`ceil()` rounds a number upwards to the nearest integer.
```js
var a = 0.5;
var b = ceil(a);
console.log(b);
```

## floor
```js
var a = 0.9;
var f = floor(a);
console.log(f);
```

## Round
```js
var a = 0.49;
var b = 0.5;
console.log( round(a) ); // 0
console.log( round(b) ); // 1
```

## Min 
```js
var a = 12;
var b = 24;
console.log( min(a, b) );
```

## Max
```js
var a = -8;
var b = -20;
console.log( max(a, b) );
```

<!--
note to myself: 
  create examples to visualize each function. 
  as in shaping function in glsl.
-->
