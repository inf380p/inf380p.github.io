---
layout: post
author: JohnCBMeyer
title: "John's Ninja Turtle Class Extension"
---

# My class extension turtlehack
The first thing I did was replace the `draw_square` method with the `draw_polygon`
method:

```python
 # A method for drawing an arbitrarily many-sided polygon
  def draw_polygon(self, sides, length, x=None, y=None):
    # Draws polygon in place unless a new location is specified
    self.goto(x if x is not None else self.xcor(), y if y is not None else self.ycor())
    self.pendown()
    for i in range(sides):
      self.forward(length)
      self.right(360/sides)
    self.penup()
    self.hideturtle()
```

This really took some work to get right. At first, I wrote this so that the user
needed to specify a `goto()` location to begin drawing, but that felt wrong. I knew
I was going to add a parameter that instantiated the class at a specific location.
Given that, it only seemd appropriate that `draw_polygon` would draw in place unless
otherwise specified.

The first thing I tried was using `self.xcor()` as a default value for the `x`
argument. However, that threw an error. After looking into it, that's apparently
a no-no. Python won't let you include `self` method calls as default arguments,
because the defaults are evaluated when the method is defined and `self` can change
between then and being called. So, I found the solution to set the default to 
`None`, then using an `if` statement in the method definition to set the value
to `self.xcor()`. 

That was the only real hurdle in this exercise. I had already written the 
`draw_polygon` function for an earlier exercise, so I just included it as a new 
method. Then, I created four new `NinjaTurtle`s, named Leonardo, Raphael,
Donatello, and Michelangelo.

The complete trinket can be found below:
<iframe src="https://trinket.io/embed/python/a87baeb349" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
