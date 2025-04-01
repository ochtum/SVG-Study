## This repository was created for learning SVG animation.

### 001_SVG_練習.svg
An SVG created using [Inkscape](https://forest.watch.impress.co.jp/library/software/inkscape/) to learn SVG.

### 002_SVG_Animation_Practice.svg
An SVG where I experimented with moving elements to create animations.

### 003_SVG_Text_Animation_Practice_01.svg
An SVG created using [Inkscape](https://forest.watch.impress.co.jp/library/software/inkscape/) with handwritten-style animations applied to text.

### 003_SVG_Text_Animation_Practice_02.svg
An SVG where I adjusted the position and size of the handwritten-style animation to make it more visible.

### 003_SVG_Text_Animation_Practice_03.svg
An SVG where I applied smoke and fire filters to a handwritten-style animation, inspired by [HOT](https://codepen.io/Alina_Niko/pen/jOobaOO) found on Codepen. Unlike the reference source, this was implemented using only SVG.


### 004_SVG_Image_Clipping_Practice.svg
An SVG where I experimented with image clipping in SVG while creating 003_SVG_Text_Animation_Practice_03.svg.


## Meaning of SVG Elements

### Inside the `d` Attribute

- `x` represents the vertical axis, and `y` represents the horizontal axis.
- Specified as `m x,y`.
- The difference between uppercase and lowercase commands is as follows:
  - Uppercase: Represents absolute coordinates.
  - Lowercase: Represents relative coordinates from the previous position.

#### LineTo Path Command
Draws a straight line.

##### L/l
Specifies both `x` and `y` coordinates to draw a straight line to that position.

##### H/h
Specifies the `x` coordinate to draw a straight line to that position.

##### V/v
Specifies the `y` coordinate to draw a straight line to that position.

#### Cubic Bézier Curve
Draws a smooth curve defined by four points. Use `C/c` to specify control points individually, or `S/s` to smoothly connect Bézier curves.

##### C/c
Specifies two control points and an endpoint to draw a curve. The starting point is the endpoint of the previous path. Each point is specified as `[x,y]`, separated by spaces.<br>
Example:<br>
```
c 1.15387,-0.42627 2.28938,-0.8746 3.40651,-1.34497 1.12448,-0.47772 2.28938,-0.79743 3.49471,-0.95912
```

##### S/s
Uses the reflection of the second control point of the previous `C` or `S` command as the first control point. The first control point can be omitted.

#### Quadratic Bézier Curve
Draws a smooth curve defined by three points.

##### Q/q
Uses one control point to draw a simple curve (not as complex as a cubic Bézier curve).

##### T/t
The control point is inferred from the previous curve command, so it can be omitted. Only the endpoint needs to be specified to draw the curve.

#### Elliptical Arc Curve
Draws a curve defined as part of an ellipse.

##### A/a

```
A 6 4 10 0 1 14,10
```
In the above example:
- The first two numbers represent the radii of the ellipse (`rx:6 ry:4`).
- The next number represents the angle of the ellipse relative to the X-axis (`angle:10`).
- The next two numbers are flags that determine how the arc is drawn:
  - `large-arc-flag:0`: Specifies whether the arc is large (`1`) or small (`0`).
  - `sweep-flag:1`: Specifies whether the arc is drawn clockwise (`1`) or counterclockwise (`0`).
- The last part specifies the endpoint coordinates (`x:14, y:10`).

This command cannot draw a complete circle, so to draw a full circle, you need to connect two arcs like this:
```
A 6 4 10 0 1 14,10
A 6 4 10 1 0 14,10
```

#### ClosePath

##### Z/z
Draws a straight line from the current position to the starting point of the path. For example, in a triangle, after specifying three points, you would normally draw a line back to the starting point. However, this connection may appear unnatural. Using the `ClosePath` command ensures a smooth connection back to the starting point.

### Inside the `filter`
#### feImage
Outputs the specified image to the destination specified by `result`.

#### feComposite
Combines inputs using the operator specified.

#### feDisplacementMap
Receives an input and specifies the strength of the displacement using `scale`.

## Reference Pages
https://www.ibnet.ne.jp/column/web/201008/

http://inkscapedesign.web.fc2.com/basic/move.html

https://liginc.co.jp/312143
https://qiita.com/m_shinada/items/b18f41972120c3caeb69
https://qiita.com/chitomo12/items/10e251c8ac470dad8541

https://developer.mozilla.org/ja/docs/Web/SVG/Attribute/d
