# Convert from Illustrator to p5.js code
If you have a complex shape that is hard to draw by plotting points one by one, you can create first in Illustrator, then translate the shapes to p5.js codes. There is no simple way to do this in p5.js yet, but, if you follow a few extra steps, you can replicate your Illustrator paths in p5.js.

  1. Draw a path in Illustrator.
  1. Save as, and choose SVG as file format.
  1. In the save dialog, click on SVG Code.
  1. Copy the SVG code. All we need is a line that starts with `<path class=...`.
  1. Visit this link: http://www.professorcloud.com/svg-to-canvas/
  1. Paste the SVG code in the text box.
  1. Click convert.
  1. Copy the generated code.
  1. This is a html5 canvas code, which is different from p5.js code.
  1. replace any `ctx.moveTo()` or `ctx.lineTo()` with `vertex()`.
  1. replace any `ctx.bezierCurveTo()` with `bezierVertex()`.
  1. Remove any `ctx.` prefixes.
  1. round the numbers to integers. (i.e. `169.999999999` to `169`.)
  1. surround the code with `beginShape()` and `endShape()`.
  1. It should work now!
