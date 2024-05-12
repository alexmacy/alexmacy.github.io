The purpose of this was to create an homage to a print by RF Dahl while also becoming more familiar with D3.js and how it interacts with the DOM.

One of the sliders adjusts the size of the circles and the other adds or removes circles. The shuffle button randomly relocates all the circles. And you can move individual pairs of circles by either clicking and dragging, or by double clicking to make it move on it's own.

This was an opportunity to experiment with: 
    - randomly generating paired SVG elements, placed in relation to each other's location, and to stay bound together when moved.
    - working with event listeners
    - slider and number inputs 
    - having the visualization react to the inputs in real time
    - dragging circles to new locations, and having the paired circle follow
    - re-arranging the circles to random locations both individually (by double-clicking), or all at once by clicking the 'shuffle' button
    - incorporating transitions into the shuffle
    - when reducing count, removing the circles in numerical order rather than re-drawing the whole thing
        - this also leaves the remaining circles in their place rather than removing and redrawing
    - incorporating a slider to change the radius of the circles in real time
