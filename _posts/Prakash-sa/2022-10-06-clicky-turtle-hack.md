---
layout: post
author: Prakash-sa
title: "Clicky Turtle Hack"
---


It will ask for the input and make polygon with the turtle.

<iframe src="https://trinket.io/embed/python/5bc112c344" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


```
import turtle
from animations import setup

chair = turtle.Turtle()

myscreen = turtle.Screen()
setup(myscreen)


side_number = int(input("How many sides are in this polygon?"))
total_angle= 180*(side_number - 2)
#print(total_angle)
#print(total_angle/side_number)

side_number_1 = side_number

world_size = (side_number/2)*100
chair.getscreen().setworldcoordinates(-world_size,-world_size,world_size,world_size)

chair_color = input("What color should polygon be now?")
chair.color(chair_color)

while (side_number_1 > 0):
  # chair.fill(True)
  chair.left(180-(total_angle/side_number))
  chair.forward(100)
  side_number_1 = side_number_1 - 1



chair.fill(False)
  ```
  
Prof. Elliot dectated the formula for the polygon in the last class so I create this tutle hack.

Initially I face the problem to implement it but finally after lot of troubleshooting I have done it.
