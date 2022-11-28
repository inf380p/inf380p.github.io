---
layout: post
author: JULIIRA
title: "JULIIRA's Clicky Turtle and Reflection"
---

This exercise helped me finally understand functions and how to use them. While
I'm still not an expert in functions, I at least understand the basics better now. 

Here is my lightbulb moment with functions:

```
def instructions():
  time.sleep(2)
  tina.clear()
```

Since I have a lot of text in the setup screen, I know I would have
to use the sleep() and clear() codes a lot so I made a helper function
for it so I wouldn't have to keep rewriting the same code and to
save time. 

One of the frustrating parts of this exercise was trying to figure out what
I wanted to do with my turtle. At first, I was going to hide the turtle
and let users find it but I was having difficulty figuring out how to
set up the code to help users find the hidden turtle so I gave up.

Initially, I was having trouble with creating helper function codes, but
once I figured out I was having fun making a few.

Here's a few that I have made for this turtle:

This code allows users to drag Tina on the screen and to doodle. 

```
def clicky(x, y):
  tina.ondrag(None)
  tina.goto(x,y)
  tina.ondrag(clicky)
```

```
def tina_stamp():
  tina.stamp()

def clear_screen():
    tina.clear()

myscreen.onkey(tina_stamp, 's')
myscreen.onkey(clear_screen, 'c')
myscreen.listen()

```
I was trying to make a code where the keys can move the turtle to where users
want without it drawing on the screen but I couldn't figure out how to do it, 
but maybe one day.


Then, I started playing around with the code on the Clicky 
Turtlehack materials page, I decided wanted to make a drawing 
turtle instead. Here is my code for this exercise:

<iframe src="https://trinket.io/embed/python/d4d780771d?start=result" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
