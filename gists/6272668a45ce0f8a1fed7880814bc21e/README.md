This came from watching Sameer Farooqui's <a href="https://youtu.be/K14plpZgy_c" target="_blank">tutorial on how to use using Spark SQL and DataFrames</a>.

It shows the rate of false alarms - calls where the final classfication was one of 'No Merit', 'Gone on Arrival', 'Unable to Locate', 'Cancelled', or 'Duplicate'. The blue dots are the locations of SFFD fire stations, and the city has been divided up into the neighborhoods as per the data provided SF OpenData. 

This was done as a way to experiment with Spark and creating visualizations within Databricks' community edition, but I exported the result of my Spark SQL query so that I could post it here as well. There is a noticeable increase in 'false alarms' towards the end, although I'm not sure why that is, I'm gueesing it may have something to do with better record keeping... 

On my wishlist - or for another day:
* Draw voronoi-style territories based on the locations of the fire stations, colored by number of calls within their borders.
	* Possibly incorporate data about the responding station when they responded to a location outside of their voronoi territory.

* Voronoi territories like above, but adjusting the polygons so that all the events are evenly distributed among the different fire stations and their voronoi territories.