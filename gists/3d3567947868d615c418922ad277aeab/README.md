I've been wanting a way to show the original state borders after the transition, so I created another layer that appears when transitioning to the voronoi shapes. There's a bit of a bug with how some of these borders are not appearing - like where "New Wyoming" is above part of old Nebraska.

This seems to be related to the order that the states are rendered...

---

#### from <a href='http://bl.ocks.org/micahstubbs/'>micahstubbs</a>'s version of <a href='http://bl.ocks.org/micahstubbs/275b480d6e9c860c0d0f15a9accc57ca'>United States of Voronoi Tweening</a>:

a small iteration on [@alexmacy](https://twitter.com/alexmacy)'s [United States of Voronoi Tweening](http://bl.ocks.org/alexmacy/50d4ab8dd53d13a00d5d8f1b6393f083) that transitions the colors of the pologons, polygon borders, and state-capitol points

playing with ways to highlight the differences between the geographic shape and the Voronoi shape of each US state

---

#### Original `README.md`

---

This is another version of the shape tweening from <a href='http://bl.ocks.org/alexmacy/06cf037853999219cd82bc79edc4aee6'>this block.</a> Inspired by Jason Davies' <a href="https://www.jasondavies.com/maps/voronoi/us-capitals/">United States of Voronoi.</a>

The transition I had previously used for shape tweening plots the points along the new shape proportionally to where they were along the original shape. This potentially results in rounded or skipped corners, so I had to figure out a new way to do it.

The new transition used here draws the destination shapes by plotting the points form the old shape equally along each side of the new shape. The result isn't always as clean of a transition, but it's still pretty smooth and the resulting shape is free from any rounded or skipped corners. 

I also put both transition functions in the standalone file `shapeTween.js` to be able to easily reuse it later.
