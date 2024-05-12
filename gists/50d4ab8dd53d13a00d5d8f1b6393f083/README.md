This is another version of the shape tweening from <a href='http://bl.ocks.org/alexmacy/06cf037853999219cd82bc79edc4aee6'>this block.</a> Inspired by Jason Davies' <a href="https://www.jasondavies.com/maps/voronoi/us-capitals/">United States of Voronoi.</a>

The transition I had previously used for shape tweening plots the points along the new shape proportionally to where they were along the original shape. This potentially results in rounded or skipped corners, so I had to figure out a new way to do it.

The new transition used here draws the destination shapes by plotting the points form the old shape equally along each side of the new shape. The result isn't always as clean of a transition, but it's still pretty smooth and the resulting shape is free from any rounded or skipped corners. 

I also put both transition functions in the standalone file 'shapeTween.js' to be able to easily reuse it later.