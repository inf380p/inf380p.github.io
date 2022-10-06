---
layout: post
author: Rowan_Loft
title: "Rowan-Loft's Clicky Turtle"
---

For my turtle hack, I decided to create a somewhat simple call and response program that uses parts of my previous "Stars in Space" code from the funciton excercise and post, user input (both clicks and keys), and the `random` library to mild success. In order to help readability and establish succinct code role, I divided the code into three categories: `main.py` which called functions from to-be discussed modules, *user-call defines* such as `onkey` and `onclick`, and the simple commands that allow the program to listen to external stimuli such as the mouse and keyboard. 

```
lofty = turtle.Turtle()
lofty.shape("turtle")
lofty.hideturtle()

myscreen = turtle.Screen()

# calls setup
setup(myscreen)

# my clicky function:
def clicky(x, y):
  star(x, y)

myscreen.onclick(clicky)

# a function for key presses
def fill_the_sky():
  populate_stars()
  populate_stars()
  populate_stars()
  
# defining the binding for key press
myscreen.onkey(fill_the_sky, 'c')

myscreen.listen()
```

my `animations.py` was simply used for calling the commands needed for executing on-screen user prompts.

```
def setup(screen):
  
  screen.bgcolor("black")
  
  # lefty is my setup turtle
  lefty = turtle.Turtle()
  # hiding lefty for setup
  lefty.hideturtle()
  
  lefty.color("white")
  lefty.penup()
  lefty.goto(0,-100)
  lefty.write("Click to place a star in the sky", None, "center", "12pt bold")
  time.sleep(3)
  lefty.clear()
  lefty.write("Press c to fill the night", None, "center", "12pt bold")
  time.sleep(3)
  lefty.clear()
```

the `myfile.py` module is where I ended up spending most of my time banging my head against the wall trying to get trinket to call on the `random` commands to execute code using generated lists in order to create stars where users clicked on the screen. Unfortunately, I ran into multiple errors that had to do with missing definitions, random being un-executable due to not being a number when plugged into a function like `rainy.color(random.choice(c))`, and the same issue with random size. 

```
t = [7, 11, 17, 21]
c = ["red", "yellow", "white", "grey", "goldenrod", "orange", "brown", "green", "pink", "blue"]
#in another program, I was able to use my "t" and "c" list to generate a random color and size star, but not here?

def star(x, y):
  #rainy will be drawing the stars click stars
  rainy = turtle.Turtle()
  rainy.hideturtle()
  
  #star draw command
  rainy.penup()
  rainy.color("red")
  rainy.fillcolor("yellow")
  rainy.goto(x,y)
  rainy.pendown()
  rainy.begin_fill()
  rainy.right(144)
  for i in range(5):
    rainy.forward(10*2)
    rainy.right(144)
    rainy.forward(10*2)
  rainy.end_fill()
  rainy.setheading(0)
  
#a new star draw command for a test
def draw_star(color, size, x, y):
  turtle.penup()
  turtle.color(color)
  turtle.fillcolor(color)
  turtle.goto(x,y)
  turtle.pendown()
  turtle.begin_fill()
  turtle.right(144)
  for i in range(5):
    turtle.forward(size*2)
    turtle.right(144)
    turtle.forward(size*2)
  turtle.end_fill()
  turtle.setheading(0)

#a test for .random
def populate_stars():
  draw_star(random.choice(c), random.choice(t), random.randint(-200, 200), random.randint(-200, 200))
```

When running the code, I was able to get the `random` code to work with key clicks, but for some reason I was not able to do the same with mouse clicks and instead had to give strict definitions to the creation of those stars, which is why they all appear as red outlined with yellow fill, but why pressing "c" on the keyboard creates a number of different types of stars. 

Not yet quite sure if I'm missing something simple or if I'm trying to do something that turtle can't recognize because I'm missing out on the necessary code, but I'm looking forward to trying to get it figured out in the future. I'd like to come back to this simple program to integrate more random generation that include rotating stars and adding the `random` functions to on-click execution.

Here is the full program. . .

<iframe src="https://trinket.io/embed/python/638114959e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
