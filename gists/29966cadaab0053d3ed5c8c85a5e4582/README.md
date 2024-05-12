This is another in a series exploring how to calculate and display the combinations of multiple waves. See the previous blocks:

- <a href='http://bl.ocks.org/alexmacy/c5d36ac67eee2ca7b69824f74fb501d5'>Compound Radial Waves
</a>
- <a href='http://bl.ocks.org/alexmacy/03547a3e7498dbe3690b7eb35578022b'>Compound Waves</a>

This makes a radial rendering of the compound wave made from three different frequencies. The resulting wave can be very long - easily getting above 100,000 or even above 1,000,000 points! That's why the sliders are limited to a maximum of 100 each. This is way beyond what can cleanly be done with SVG, so I used canvas for the rendering. But that was still running slow, so I removed d3 altogether and rebiult it in VanillaJS.

The base frequencies are randomly selected when the page is loaded, so refreshing will produce a new compound wave, and there's also capability to save a combination of frequencies to be accessed later. The button at the bottom will bring up a prompt with a URL for current waveform - note that this will only work when loaded 'raw' <a href="https://bl.ocks.org/alexmacy/raw/29966cadaab0053d3ed5c8c85a5e4582">here</a>.	

For example:
<a href="https://bl.ocks.org/alexmacy/raw/29966cadaab0053d3ed5c8c85a5e4582?78,30,49">78,30,49</a>