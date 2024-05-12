This is a big update from the previous version, including the addition of sound!

*Please note that this is part of an ongoing series of experiments. While it should run smoothly in Chrome, it hasn't been optimized for other browsers at this time.*


Previous blocks in this series:

- [Compound Radial Waves v2](http://bl.ocks.org/alexmacy/29966cadaab0053d3ed5c8c85a5e4582)
- [Compound Radial Waves](http://bl.ocks.org/alexmacy/c5d36ac67eee2ca7b69824f74fb501d5)
- [Compound Waves](http://bl.ocks.org/alexmacy/03547a3e7498dbe3690b7eb35578022b)

One note on the sound synthesis: I started with generating the sound for the compound wave by calculating each sample and pushing it to the sound buffer. The idea being that it would be a more 'pure' demonstration of how sound waves interact by synthesizing the sound using an algorithm rather than using Web Audio's built-in oscillators. But this was causing a lot of problems. Namely, the longer waves would never be able to fit in the buffer unless treated like a queue - but that was causing a lot of clipping when changing the frequencies due to difficulties ensuring that the waves meet at a zero crossing point. The workaround for this was to just use the built-in oscillator. 

  All that said, the end result is ultimately the same since the sound generated by the oscillators gets combined when it goes to the AudioDestinationNode.

Other features include:
  - Highlighting of the individual waves when the cursor is over its controls
  - The ability to toggle visibility of the compound wave and the individual waves
  - The sweep button makes all but two oscillators innactive adn sweeps one of them through the available frecuencies to show how the two waves interact.
  - The shuffle button shuffles all the oscillators 10 times.

  
I chose to only use three oscillators because more than that can cause the drawn compound wave to be too busy. But there's a hidden feature for adding more oscillators by running addNewOsc() in the console. This is included for stress-testing and exploring more complex combinations.