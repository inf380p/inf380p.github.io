---
layout: post
author: mchakerautexas
title: "Mufaddal's turtle class extension"
---

# Custom Turtle with Draw Polygon
My aim for this assignment was to wrap the draw polygon method I have created and iterated on in the previous classes/assignments in a class to create my own turtle library. One of the requirements of this assignment was to have the turtle start as a custom location (which would be a property of the turtle). However, the draw_polygon function I had created took a position as arguments, so I had to figure out how to get it to take the turtle's current position as starting points. There were 2 approaches that came to my head:
1. Remove the posx and posy parameters from my function, and always have it draw at the position the turtle stood.
2. Find a way to get the turtle's current position, and draw at the current position of the turtle if posx and posy were not specified. 

For the sake of generalization, I chose to go with approach 2. I wanted the user to be able to choose where to draw the shape, if need be. Approach 2 turned out to be harder than I thought. At first, I tried passing in self.pos()[0] and self.pos()[1] as default parameter arguments, but Python did not like that. It took me a while to figure out what the exact issue is, and I found out that self cannot be referenced from within function parameters. So, I finally settled for passing in None as default arguments, and then checking if posx or posy were None to then set them to the current position. This worked like a charm, and I was able to draw four beautiful shapes:

<iframe src="https://trinket.io/embed/python/3f1514c16b" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
