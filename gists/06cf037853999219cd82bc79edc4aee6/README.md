This is an attempt at finding a way to make cleaner transitions between polygons. <a href='http://bl.ocks.org/mbostock/'>mbostock</a>'s block: <a href='http://bl.ocks.org/mbostock/3081153'>Shape Tweening</a> works excellently for morphing a shape into a circle, but not for morphing into smoething like a polygon.  I was looking for a way to do something much like his other block: <a href='http://bl.ocks.org/mbostock/1020902'>Superformula Tweening</a>, but with the ability to pass coordinates for the new shape instead of control points for the superformula to make sense of.

The three biggest challenges were:
  - The first points along the path need to be in the same general area - like if all the shapes started with their point closest to the upper left.
  - Both the incomming shape and the outgoing shape must have the same number of points or else you get unexpected results and it doesn't transition smoothly.
  - Both shapes need to have the same orientation (clockwise/negative vs. counterclockwise/positive), otherwise they seem to flip when transitioning.
   
Finding the starting points for each path was simply done by looping through the incomming shape's points to find the closest point to the start of the outgoing shape's path. Then it's just a matter of changing the order of the incomming shape's points.

For matching the number of points, I created a linear scale using the length of the outgoing shape and plotted the necessary points along the incomming shape's path proportionally to where they were along the outgoing shape's path. This required using a hidden path element '#hiddenShape' in order to be able to compare the two before rendering the new shape. Most of this is done within the converPath() function.

And matching the orientation of the shape's points was done by using d3.polygonArea(). This tells you the orientation by being either positive or negative, so some logic at the end of convertPath() decides if it should return the array as-is, or reversed. 