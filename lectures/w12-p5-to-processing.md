# Convert p5 sketch into Processing (incomplete guide)

Processing and p5.js use different languages, but the syntax is quite similar. With some manual changes, we can convert p5 sketches into Processing sketches. There is [a good guide](https://github.com/processing/p5.js/wiki/Processing-transition) to use.

Why would you want to convert to Processing?

Well, p5 works best for browser-based interactive work, but if you try to use it for print-based work, it can be a bit troublesome. In terms of performance, Processing is faster than p5 as well.

Convert only if you must. 

But what's better is that when you start a project, first think about how you want to display your work -- interactive? web-based? printed? standalone app? And choose the right language so that you don't waste your energy.

Also, it is much more important to understand the basic programming concepts than learning another language, which can become confusing. So, unless you must convert, let's stick with p5.js and focus on its strength.


## Things to change

  - `createCanvas()` to `size()`
  - `var` to different types of variables. There is no `var` in Processing!
    - `int` for integer numbers
    - `float` for float point numbers
    - `boolean` for true or false
    - `String` for a string of text
    - `char` for a single character
  - For function parameters, you have to specify their types (as above).
  - `function setup(){ }` to `void setup(){ }`
  - `function draw(){ }` to `void draw(){ }`
  - all the other `function xxxx()` definition to `void xxxx()`.
  - if your function *returns* a value, specify the return type:
    - `int xxxx()` if it returns integer
    - `float xxxx()` if it returns float
    - `String xxxx()` if it returns string
    - and so on...
  - `console.log()` to `println()`
  
  Here is [an example code](../../files/porting-p5-ex.zip) that we will use in class for converting/porting.
