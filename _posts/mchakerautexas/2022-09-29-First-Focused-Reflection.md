---
layout: post
author: mchakerautexas
title: "Muffu's First Focused Reflection!"
---

## Focused Reflection
In the first class exercise, when we were drawing shapes like circle and squares, it got me thinking could I build a function that makes a regular polygon. This thought put me in a huge rabbit hole of math and geometry but luckily I was able to come up with something. 

The first intuition I had was that to draw any polygon, all we need to do is figure out what angle the turtle has to turn for each side. That is just the internal angle of the regular polygon. At this point, I googled and found the formula for calculating that. At this point, I had a program that could draw polygons, but their sizes were all over the place. Each edge was a fixed size, so by the time I started drawing huge polygons, it would explode in size and would be essentially invisible.

The next(and hardest) part was to figure out how to normalize the size of the polygon. After a lot of research, and a recap of the fundamentals of trigonometry, I was able to figure out a formula for the length of the side of a polygon, given a fixed radius for the circle in which it would fit inside. This circle was my measure of the overall size of the polygon.

Finally, I was able to create a function that draws any regular polygon. A bonus point is that it was worth extra credit :D

Code:
<iframe src="https://trinket.io/embed/python/1377ae1ec1" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
