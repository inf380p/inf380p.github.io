---
layout: post
author: haley-triem
title: "Haley's Etch A Sketch Reflection"
---
# Only after hours of coding, did I realize that I basically made a glorified Etch A Sketch ...
I don't know what's up with me and coding 90's toys ... an Etch A Sketch is a little screen that allows you to draw using knobs. When you want the drawing to clear, you shake the screen. For this project, I wanted to experiment with creating a paint tool, like Microsoft paint.

## My main objective was figuring out how to make a turtle change colors based on where the user clicks:
I started out by trying to define different color options and call on those options; I looked up examples online of people testing click events to change `screen.bgcolor()`, and then tested changing `tommy.color()` to red. This completely failed because I was trying to both change `screen.bgcolor()` and `tommy.color()` and did not define a healthy function. (reference: https://www.geeksforgeeks.org/turtle-onscreenclick-function-in-python/)
``` python
import turtle
screen = turtle.Screen()
tommy = turtle.Turtle()

# define color red as a function
def fun red(x , y):
  tommy.color("red")
 
# the background color would be red in this test
  screen.bgcolor("red")
  
# test calling with a click event
  tommy.onscreenclick(red)
```
I also knew I needed to use conditionals ... I tried again, and used `(0,0)` to test if clicking on the origin would affect color change. I decided to use a `print()` statement just to test if I was setting up my conditionals correctly.
``` python
def red(0, 0):
  if tommy.onscreenclick(red):
    print("epic")
```

I was very lost on defining a function using coordinates, but finally came to something that changed tommy's color when I clicked. the varibles in the parenthesis weren't really needed, in retrospect. It could have just been `tommy.onscreenclick(red)`.
``` python
def red(x, y):
  tommy.color("red")
 
tommy.onscreenclick(red(0,0), btn=1, add=None)
```

I did some more testing by having the program output coordinates of where I clicked:
``` python
def red (x, y):
  tommy.goto(x, y)
  print(x, y)
  
tommy.onscreenclick(red)
```

And then I began to test setting specific bounds in which one had to click a certain box to get a certain result:
``` python
def red(x, y):
  print(x,y)
  if (x<0):
    print("yay")
    
tommy.onscreenclick(red)
 ```

I used this testing to set bounds for different sections of the screen that will change the color of your turtle if you click them. A cascading set of `if` statements allowed me to make bounds on both the x and y coordinates. I didn't delete the `print()` function because I wanted to keep an eye on where I was clicking while testing. Finally, I added a simple movement with the arrow keys, almost exactly the same as Prof. Elliott showed us. Perhaps in the future, movement can be generated through click events, though (see "Looking ahead" below) ...
``` python
import turtle
from background import setup

# tell the turtle which screen
myscreen = turtle.Screen()

# set up the background design
setup(myscreen)

# tell users how to use the program
print("Use WASD keys to draw! Use mouse to select color!")

# tommy will draw ... let's get to know him
tommy = turtle.Turtle()
tommy.speed(10)
tommy.color("#736C87")

# let users pick colors
def color(x, y):
  print(x, y)
  #yellow
  if (-180 < x < -155):
    if (150 < y < 175):
      tommy.color("#FBF8CC")
  #warm green
   if (-180 < x < -155):
    if (120 < y < 145):
      tommy.color("B0FBC0")
   # etc. with more colors ...

# listen for a click
myscreen.onclick(color)

# defining moving to draw
def go_left():
  tommy.left(10)

def go_right():
  tommy.right(10)

def go_forward():
  tommy.forward(10)

def go_backward():
  tommy.backward(10)
  
#  pair functions with keys
myscreen.onkey(go_left, 'a')
myscreen.onkey(go_right, 'd')
myscreen.onkey(go_forward, 'w')
myscreen.onkey(go_backward, 's')

myscreen.listen()
```
A background setup was used in combination with the code; thanks sally for doing all the hard work!
``` python
import turtle
myscreen = turtle.Screen()

# define a screen set up function that can be used in the main code:
def setup(screen):

  sally = turtle.Turtle()
  sally.hideturtle()

  # draw the interface here, including all of the color boxes that correspond with the click coordinates.
```

# The "finished" program, which still has plenty of room for experimentation!

<iframe src="https://trinket.io/embed/python/5248e75644" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## How could I have made the current code better?
I think that there could have been ways to mitigate the repetitiveness of drawing each color option square individually. In retrospect, I should have looked into coding a `square(x,y,color)` function that draws a square wherever you decide, and fills it with whichever color you specify. I am unsure how to write a function with both specified coordinates _and_ color variables, but I am sure there's a way.

## Looking ahead ...
It took me an embarassingly long time to figure out the colors (7+ hours, oof), but now that I have those down I think there's room to add drawing tools that are tied to clicking specific coordinates on the map (fill tool, line tool, circle tool, etc.).

I also want to figure out how to let users paint by clicking and dragging, while simultaneously still being able to click to choose colors and tools. But if users can click and drag to draw, I probably would have to set up conditionals where if they were in a certain coordinate range (i.e., the drawing board) the turtle would listen for a click and drag, and if they were in another coordinate range (i.e., the color and tool selection), the turtle would listen for a click to choose said color / tool.

Thinking about interface: it would be easier with a square function to move around color choice boxes as necessary. Additionally, regardless of the conditionals mentioned above, I simply need to put bounds around the drawing board to stop users from wandering up into interface when drawing.

Finally, I think it would be fun to hide some easter eggs! What if the user accidentally clicks a secret spot on the interface? Maybe I could get the turtle to do something fun, like change shapes! Maybe if the users spin in a full circle, it breaks the bounds of the drawing board, allowing them to draw all over the interface! I think I have some opportunities to experiment and make this code fun :)
