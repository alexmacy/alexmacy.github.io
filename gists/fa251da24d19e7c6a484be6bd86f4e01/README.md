This is an attempt to add thumbnail previews to <a href="http://bl.ocks.org/mbostock/afecf1ce04644ad9036ca146d2084895">Mike Bostock's version</a> of <a href="http://bl.ocks.org/micahstubbs/948378950dd7b3e31e8cda3b33ebbcc8"> Micah Stubbs' block</a>. The tooltip also utilizes some code from the tooltip on <a href="http://bl.ocks.org/dhoboy/f9b212b40aa52386802621b53fc3fdab">Daniel Overstreet's Beijing Air Quality 3</a>.


Hovering over a node loads that block's thumbnail in a tooltip. There are a couple issues that need fixing:
  
  - Need to add a placeholder of sorts for blocks that don't have a thumbnail.


forked from <a href='http://bl.ocks.org/mbostock/'>mbostock</a>'s block: <a href='http://bl.ocks.org/mbostock/afecf1ce04644ad9036ca146d2084895'>Blocks Graph</a>


I added some CSS in the head for the tooltip and then defined the tooltip @ line 36:

	var tooltip = d3.select("body")
	    .append("div")
	      .attr("class", "tooltip")
	      .style("position", "absolute")
	      .style("z-index", "10")
	      .style("visibility", "hidden");

Also made a function for fetching and displaying the image @ line 126:

	function loadTooltipThumb(d) {
		tooltip.select('*').remove();
	
		var thumbnailURL = 'https://bl.ocks.org/' + (d.user ? d.user + "/" : "") + 'raw/' + d.id + '/thumbnail.png';
	  
		var top = d3.event.pageY - 150;
	  
		tooltip.style("top", top + "px")
	    	.style("left", d3.event.pageX + 40 + "px")
		    .style("visibility", "visible")
		    .append('img')
		    .attr('src', thumbnailURL)
	}

...which gets called in the 'mousemoved' event @ line 98

There's also something in the logic at line 93 and shrunk the searchRadius @ line 26 to hide the tooltip when not hovering over a node.
