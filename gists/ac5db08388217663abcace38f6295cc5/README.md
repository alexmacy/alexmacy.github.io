This dashboard was made for testing a couple different visualizations. Mainly a sortable data table and a stacked single-line row charts. It displays data about U.S Presidents, their party affiliations, duration in office, etc.

Pie charts are very convenient, but are not ideal for accurately displaying data - not to mention have a steadily decreasing amount of fans, so I wanted something that would easily display comparable percentages of a whole, while not requiring less space than is needed for a histogram.

That brought me to making a stacked row chart that falls somewhere in the middle of the two. To do this, I repurposed a bar chart, gave all the bars the same height, and adjusting their width and placement based upon their percentage of the whole. The top row chart resizes based on the time period selected, and the bars on both charts fade when either outside of the selected time period or if their party is not selected.

This is the same as <a href='http://bl.ocks.org/alexmacy/c0302e4d78cebc193840'>This dashboard</a>, but written in ES5 for compatibility with more browsers.