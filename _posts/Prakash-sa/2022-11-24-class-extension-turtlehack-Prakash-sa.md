---
layout: post
author: Prakash-sa
title: "Prakash's Turtle class extension"
---

I wrote the helix spiral code with turtle.
```
def helix_spiral(self, number,color='black', x=None, y=None,speedN=2):

  self.pendown()
  self.color(color)
  self.speed(speedN)

  # program to draw the sprial helix pattern
  for i in range(number):
    self.circle(5*i)
    self.circle(-5*i)
    self.left(i)

  self.penup()
  self.hideturtle()
```

I made the extend the turtle class by coded the TurtleExtension class. At first time, I forgot to add turtle.Turtle in the class argument. After debuging and researching I realised my mistake and added that part.

I have taken the x coordinate, y coordinate, color, speed of the turtle and number of helix spiral from the user.
I have also added the interface to provide the flexibility wheter user wants to continue the program or exit it.



<iframe src="https://trinket.io/embed/python/a13f666c29" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


