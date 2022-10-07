---
layout: post
author: jpmartinezutexas
title: "jpmartinezutexas's first post!"
---

Hi! I am John Paul Martinez, a 2nd year in the MSIS program, studying UX design and research. Welcome to my clicky turtle hack reflection post. I will go over some of 
my code and explain my project. 

# Clicky Turtle Hack
### Heres my code
<iframe src="https://trinket.io/embed/python/0adb9080eb" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Reflection Time 

My project this time was two turtles, one that you could control with the W A S D controls, (up, left, down, right) in that order, as well as one that you used the mouse
to control. The red WASD turtle, which I call Clyde, is just used to walk and move around. He always appears over the drawings of Tina - the mouse key. I made it this way
because in most games you use WASD to move, and this could be the start of making some sort of map-drawing feature, where the player will always appear over the map.
However, for this one I have Tina draw a circle of
a random color at where you click. 

At least, it does that when you click slowly. 

When you click through much faster however, it makes a very dynamic animation reminiscent of old Windows screensavers. 

This is an example of a helper functin I wrote to draw the random circle at the point clicked.  

```python
# Helper Function
def go_draw_circle(x, y):
    tina.color(random.choice(colours))
    r = 50
    tina.goto(x,y)
    tina.circle(r)
```

Although it's pretty short, having 6 lines to define a function can add up if you put all of them in the same file. That is why I decided to make another file called
helpers.py which I imported this from. The code is much cleaner, and frankly, much easier to navigate with multiple files. Having all of the helpers in one dedicated 
file makes it much easier to find when I can just tab to that as opposed to searching through one long text of just a main.py file.

Overall, I had a good time with this project. I of course had some unexpected hiccups getting the function to work, but that was because I had forgot to originally 
import the necessary modules 

```python
import turtle
import random
tina = turtle.Turtle()
tina.shape("turtle")
```

Ultimately, I am excited to work with more turtle programs, and am interested to make a multiplayer turtle game. Maybe one can use WASD, one can use the arrow keys,
or one can use WASD and one can use the mouse to assist the WASD. Either way, I am happy with the outcome of the project. 
