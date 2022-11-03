---
layout: post
author: unixEnthusiast
title: "unixEnthusiast's first post!"
---

I feel that this course has been a solid refresher on the core concepts of programming and software developement for me. Understanding these concepts in my opinion is extremely important and something which can build a solid base always goes a long way. The lightbulb was definetely the fact that I need to be fluent and understand these concepts rather than be perfect in it. There are various aspects especially version control and thinking like a developer which I wanted to revisit and happy to see those topics being tackled on. I remember the way which the groups discussed various ways to program the turtle exercise and that showed such great team work. I was able to create functions and sub-functions which made the code simpler to read while also modularizing it. I feel some youtube tutorials are also helpful to combine knowledge gained from the class as well.

Code to draw a diamond shape:

~~~
def draw_diamond(turtle, color, size, x, y):
  turtle.penup()
  turtle.color(color)
  turtle.fillcolor(color)
  turtle.goto(x,y)
  turtle.pendown()
  turtle.begin_fill()
  turtle.left(45)
  turtle.forward(size)
  turtle.left(90)
  turtle.forward(size)
  turtle.left(90)
  turtle.forward(size)
  turtle.left(90)
  turtle.forward(size)
  turtle.end_fill()
~~~
  
Further function to draw 4 diamonds to forma a larger diamond with the new function:

~~~
def diamond_pattern(turtle, color1, color2, color3, color4, size, x, y):
  draw_diamond(turtle, color1, size, x, y)
  turtle.left(45)
  draw_diamond(turtle, color2, size, x, y - sqrt(2)*size)
  turtle.left(45)
  draw_diamond(turtle, color3, size, x + (0.5)*sqrt(2)*size, y - (0.5)*sqrt(2)*size)
  turtle.left(45)
  draw_diamond(turtle, color4, size, x - (0.5)*sqrt(2)*size, y - (0.5)*sqrt(2)*size)
~~~

Line indentations and code formatting are sometimes things which bug me in python but with a proper IDE like PyCharm or VSCode, those issues can also be resolved. Branhing and managing repositories on github are still a bit confusing to me and I am hoping to understand more about it.

Embedding for the trinket code:

~~~
<iframe src="https://trinket.io/embed/python/a30cbd6130" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
~~~

I feel the format of this course is perfect for begineers or even for someone who needs a good refresher on it. I am confident to learn more and more as the course goes on.
