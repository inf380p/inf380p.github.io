---
layout: post
author: pranithavallabhaneni
title: "Pranitha's extra credit class extention turtle hack"
---

Link of my trinket program is given below:

<iframe src="https://trinket.io/embed/python/21ae8fdcc2" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>




For the class extension turtle hack I want to change the shapes and colors and starting position of the resulting object in the __init__ method as given in the guide. Then, I instantiate four objects like circle,square,traingle,rectangle.Then, I want to use random module to my class that enables it to make a shape when called. I searched about random module and  how to initiate objects in python,it's implementation and the way it works using some online sources.

```
def start():
  colors = ['red','blue','green','black']
  shapes = ['circle','square','triangle','rectangle']
  trtl_objects = []
  x=-150
  y=-50
  for i in range(4):
    x = x+50
    y = y+50
    trtl_objects.append(NewTurtle(x, y, colors[i]))
  
  for i in range(len(trtl_objects)):
    trtl_objects[i].draw_shape(shapes[random.randrange(0,len(shapes))])

```








As mentioned I instantiated my custom Turtles in a loop. As a end loop result I managed to get my result which is successfully using random module in creating my selected shapes with given colors which changes it's shapes and colors randomly everytime you run the program without any bugs.

