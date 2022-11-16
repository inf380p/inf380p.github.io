---
layout: post
author: JULIIRA
title: "Interface Draft"
---

# Embedded trinket 

<iframe src="https://trinket.io/embed/python/a0d23b086c" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


## Modified list of milestone (original list was unorganized so here's a cleaner ver. of my milestone list):

_X_  create shapes avatars for game and set them in position (ex: turtle is a turtle, apples is a circle and cars are squares)

_X_ create turtle lives

__ figure out how to make turtle, turtle lives and apples disappear when they interact with other shapes

__ Add time limit to game

_X_ Make the turtle move when user uses mouse or keys

__ make the car move on a loop

__ create a loop for the game so user can play mulitiple times (aka have an iterative interface)

__ Add two more levels

__ Make help dialog

__ extend a custom turtle class 

___ create a win screen

__ Use one or more custom images (probably for the background)



# Are there any roadblocks ahead? Is there anything your group can do to help out?

So far, I am having difficulty trying to figure out how to make the turtle and apple interact. For example, 
I would like the apple to disappear when the turtle interacts with it. I would also like to see if it's possible to make the turtle disappear 
when the car interacts with it too. Also, I'm going to see if I can add a time limit to the game but this will be the last component I will add 
on the game as I am more more concerned with the issues stated above. I am also having a hard time figuring out how to add a loop so that players
can play again if they lose or win. 

However, right now my biggest issue is that every time I try to code using python3, I keep getting this error: 

```
 import tkinter as TK
ModuleNotFoundError: No module named 'tkinter'

```
Because of this issue my interface draft was completed on python as I can't get it to work on the pygame program either. 

I think my group might help me out with the looping issue.

# Are your milestones ambitious enough? Make sure to include some stretch goals.

To me, my milestones seem ambitious enough because I am still having difficulty doing loop statements so if I can figure out how to make the game
loop that will be a major milestone I have achieved all semester. Another stretch goal is figuring out how to make a win screen and how to make the
avatars disappear when they interact with each other. 

# Are your milestones too ambitious? Make sure to break down the unglamorous parts of coding into chunks that reflect the actual work to be done.

Probably. I'm still struggling on figuring out how to use animations.py and screen stuff. I am also having difficulty with loops and I'm still trying
to figure out what extend turtle class even means. In addition, there are still some parts of coding that I need to improve in (conditionals and loops). 
I was even having difficulty fixing the onclick codes but I managed to figure it out. 

```
def mouse (x,y):
  snappy.ondrag(None)
  snappy.goto(x,y)
  snappy.ondrag(mouse)
  
myscreen.onclick(mouse)

```
I am still having difficulty adding the help button, so far users can type h to get instructions on how to play the game (I might add more details 
for the help dialog such as explaining the goal of the game to the users), but now I am having difficulty getting rid of that annoying prompt box
which takes up so much of the screen space so users cannot see the whole game when the prompt box is open. For this reason, I have commented out 
myscreen.onkey(help_screen, 'h').

```
myscreen.onkey(go_left, 'left')
myscreen.onkey(go_right, 'right')
myscreen.onkey(go_forward, 'up')
myscreen.onkey(go_backward, 'down')
#myscreen.onkey(help_screen, 'h')
myscreen.listen()
```
The clicky turtle exercise we did in class helped me figure out how to use the onclick and onkey codes and they will be modified and used for the final project. 

# Are you able to keep to your plan? Looking back at what you’ve actually done, is the difference accountable to bad planning 
# (i.e. not anticipating what needed to be done), bad execution (not doing it), or something else?

I hope I'll be able to keep to my plan, but if by chance I do not achieve everything on my milestone list, it is because of my lack of skill. 

# What's next?

I plan to figure out how to make the apples and turtle disappear when they interact with other objects if possible and once I figured that out, 
I will figure out how to make the first level loop. Then, I will work on completeing everything on my milestone list.
Then, if I have time, I will try to figure out if I can insert a time limit to the game to add more difficulty. 
