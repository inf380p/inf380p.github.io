---
layout: post
author: unixEnthusiast
title: "unixEnthusiast's first focused reflection"
---

**Reflection**

It has been a fun experience for me so far looking at the familiar concepts as well as the not so familiar things like pull requests and working in a collaborative and large environment like a common repository for the website. Revieiting concepts like functions and loops has been rewarding. It gives you the ability to be creative and build fun programs. Collaborating with multiple users and reading their code helps with getting familiar with reading code in general. Also highlights the importance of writing clean code and readable comments. And the sense of accomplishment on completion of the code and successful runs is always good. Finding bugs and working through errors also helps and makes you careful in the next runs and to avoid making common errors.

I was trying to combine the concepts of functions to make mountains easier and to generate polygons in general. To do this, I went ahead to create a function to generate polygons given the starting coordinates, length of the sides, the number of sides and the fill color. Following is the function to do the same:

````
def draw_polygon(bird, x, y, length, sides, color):
  
  bird.speed(10)
  bird.pensize(4)
  bird.fillcolor(color)
  
  bird.goto(x, y)
  bird.setheading(0)
  
  angle = 360 / sides
  
  bird.begin_fill()
  for i in range(sides):
    bird.forward(length)
    bird.left(angle)
  bird.end_fill()
  
  bird.setheading(0)

````

This function can be resued to create multiple mountains and even other shapes with colors that can draw a landscape. I guess a similar approach is taken by game engines to render triangles to create game graphics. Interesting stuff.

I hope to keep learning and improving my coding skills and github posting abilities :)

**Here is my Trinket:** :turtle:

<iframe src="https://trinket.io/embed/python/83c4e2d2fd" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
