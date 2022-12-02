---
layout: post
author: Prakash-sa
title: "Prakash-sa's first focused reflection!"
---

***Reflection***

It is a great experience to learn how to code and at the same time how to contribute that code using github. I learn to use the trinket and draw the pentagon using the functionality of it. I call the draw_polygon function with the different color, size, x-coordinate, y-coordinate and speed of the turtle. I learn how to use the function and make easily understandable short code with it.



```
def draw_pentagon(turtle, color, size, x, y,speedN):
  turtle.penup()
  turtle.color("black")
  turtle.shape("turtle")
  turtle.speed(speedN)
  turtle.fillcolor(color)
  turtle.goto(x,y)
  turtle.pendown()
  turtle.begin_fill()
  for i in range(5):
    turtle.forward(size)
    turtle.left(72)
  turtle.end_fill()
  turtle.setheading(0)
```

**My Trinket:** :turtle:

<iframe src="https://trinket.io/embed/python/4a3506f161" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
