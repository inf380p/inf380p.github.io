---
layout: post
author: JULIIRA
title: "Project Update Post"
---

Trinket for current WIP:

<iframe src="https://trinket.io/embed/pygame/aa27add961" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# Old plan + New modifications (Also current milestones accomplished so far)

X create shapes avatars for game and set them in position (ex: turtle is a turtle, apples is a circle and cars are squares)

~~create turtle lives~~ 

__ figure out how to make turtle, turtle lives and apples disappear when they interact with other shapes

__ Add time limit to game

X Make the turtle move when user uses mouse or keys

X _ make the car move on a loop

__ create a loop for the game so user can play mulitiple times (aka have an iterative interface)

__ Add two more levels

X Make help dialog

__ extend a custom turtle class (I did extend a custom turtle class for one of the avatars but might do two
more for the car and turtle, still deciding)

___ create a win screen

X Use one or more custom images (probably for the background)

__create a start button using the onkey code

X import an image for either avatars or background

# Roadblocks

- I am having major difficulties in figuring out how to extend turtle class for the car and 
turtle. Every time I try to create an extend class for both, I can no longer move the 
turtle using my mouse or key for some reason. Perhaps, my group can help me figure out this issue.

- I am still having difficulty figuring out how to make the apple disappear when the turtle touches it 
and I am having the same issue with the car and turtle. Basically, I am having issues with making a collision code.

- I wanted to make a win screen but I am also having difficulty figuring out how to do that

# Are milestones too ambitious or ambitious enough?

I think some of my milestones are ambitious enough such as creating a loop for my car avatar. I couldn't 
figure out loops but now that I have learned to create one, I am sure I can create more loops.

```
def car():
  car = turtle.Turtle()
  car.shape("square")
  car.color("blue")
  car.penup()
  car.goto(-200, 0)
  car.forward(400)
  car.backward(400)
  car.speed(1)
    
while True:
  car()

```

Also, I was able to set up a background for my game (I made the background on paint and then added it to the pygame) 

```
screen = turtle.Screen()

screen.bgpic("snappys adventures.png")

```

I am also proud of myself for being able to create a turtle class for one of my avatars

```
class apple(turtle.Turtle):
   def __init__(self):
      apple = turtle.Turtle()
      apple.shape("circle")
      apple.color("red")
      apple.penup()
      apple.speed(7)
      apple.goto(-150,0)

apple = apple()

```

I am still trying to figure out how to use extend turtle class though so I haven't fully understand this code just yet. 

# Are you able to keep to your plan?

Most likely not because there are some codes that I am still trying to understand and time is ticking and I am 
running out of time. If I can't figure out how to do some of the milestones on my list, I will most likely turn in what
 I have now for my final. I will admit this is probably due to bad planning (horrible time management on my part) and bad 
execution (inability to do the codes I want and need for this project). But I did my best and I am proud of my progress so far. 
I learned so much!

# What's next? 

I will try to figure out how to create an extend turtle class for snappy (the main avatar) and make it so that 
snappy can move when I use mouse and keys. As of now, snappy is not a class but he can still move when user uses 
their mouse and keys and I already have a class for apples so that's all that matters to me for now. 

I will work on making the collison work so that the apple disappears when snappy interacts with it and snappy
 hides when the car hits it. Those are my major goals prior to turning in my final, but if I am unable to do so I
 will just turn in what I have for now. 
