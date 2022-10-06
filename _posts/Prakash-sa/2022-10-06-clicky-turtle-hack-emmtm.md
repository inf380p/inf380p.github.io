---
layout: post
author: Prakash-sa
title: Clicky Turtle Hack
---


It will ask for the input and make polygon with the turtle.


```
import turtle

chair = turtle.Turtle()

chair_color = input("What color should Chair be now?")
chair.color(chair_color)


side_number = int(input("How many sides are in this polygon?"))
total_angle= 180*(side_number - 2)
#print(total_angle)
#print(total_angle/side_number)

side_number_1 = side_number

world_size = (side_number/2)*100
chair.getscreen().setworldcoordinates(-world_size,-world_size,world_size,world_size)

filledcol = input("What color should the fill be?")
chair.fillcolor(filledcol)

while (side_number_1 > 0):
  chair.fill(True)
  chair.left(180-(total_angle/side_number))
  chair.forward(100)
  side_number_1 = side_number_1 - 1

chair.fill(False)
  ```
