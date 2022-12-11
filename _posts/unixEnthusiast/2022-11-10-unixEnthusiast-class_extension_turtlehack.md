---
layout: post
author: unixEnthusiast
title: "Nikhil's Jumping TurtleHack Extension"
---

# Class Extension for TurtleHack

I started with extending the turtle class for my custom JumpingTurtle class. Then overrride the __init__ function to make the custom changes for our turtle


```python
 #overrride init dunder function
  def __init__(self, x, y):
    
    # We set up our turtle like regular Turtles:
    turtle.Turtle.__init__(self)

    # Then, customize these things:
    self.speed(7)
    self.penup()
    self.shape("circle")
    self.color("blue")
    self.goto(x, y)
```

I then worked on the custom draw function. I thought making spiral shapes with the circles was a neat idea and took inspiration from the draw_polygon logic to decide the angle change required to draw the next set of circles. This resulted in the following function to draw the custom shape:

```python
 # Method to draw the new custom shape
  def draw_custom_shape(self, radius, num, x=None, y=None):
    
    #goto the drawing position
    draw_x = x if x is not None else self.xcor()
    draw_y = y if y is not None else self.ycor()
    self.goto(draw_x, draw_y)
    
    #start drawing the required circles
    self.pendown()
    for i in range(num):
      self.circle(radius)
      self.right(360/num)
    self.penup()
    self.hideturtle()
```

The logic to get to the x and y coordinates makes sure that if the user does not include them, the turtle does not move and not give an error for missing the required parameters.

After this was the easier task of creating the four objects with the overridden init functions and then calling the draw_custom_shape fucntion on them.

Here is the trinket for the code:
<iframe src="https://trinket.io/embed/python/1a0b97db67" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
