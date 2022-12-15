---
layout:post
author:nemothefish260
title: "Final Project Reflection"
---

# Link to my Trinket:
https://trinket.io/python/dc316e8a95

# Why I chose the turtle project:
I chose the turtle project, as opposed to the data cleaning option, because I am a visual learner and a creative person who loves combining drawings with narrative. I 
also have found the turtle projects to be more liberating than more meticulous, mathematical prompts.Right off the bat, I also knew that I wanted to
create an animal adventure game for two reasons. Firstly, a cute character/storyline would keep me engaged in the coding process, and also, the choice of a bat would 
give me the space to create a game that ideally completes the goal of educating players about the importance of this seemingly dangerous small and local animal in 
protecting the balance of the ecology. The aim is to help people empathize with an animal, whose demonization was further exacerbated after the pandemic. Simultaneously, 
the localized background of the bat would help people in thinking about climate change in a manner that is concrete and actionable. I thought that these aspects are 
important since current representations of climate catastrophe tend to paralyze with doom and gloom instead of empowering.

# The Menu:
The Menu allows the user to choose from three levels. I have also drawn a few purple bats, with the rest of the colors being largely pastel so that a friendly feeling
is evoked for the protagonist, bat character.


# Helper Dialogue, Game State and Collision:
I have also created a helper dialogue that remains consistently present and instructs the user on how to navigate the interface. A scorekeeper and a timer also constantly
update the screen in response to the  bat character's collision with the objects around them. For instance, eating an 'insect'(a colorful ball' would increase the
score by 10 and colliding with an 'insect'(another turtle) will decrease it by 10. 


```def clicky(x, y):
  
  global score
  global bat1,insects,bubbles,blossom,buttercup,scorekeeper
  bat1.goto(x,y)
  if distanceBetweenTurtles(bat1,insects) < 10:
    score+=10
    setStart(insects)
  
  if distanceBetweenTurtles(bat1,bubbles) < 10 or distanceBetweenTurtles(bat1,blossom) < 10 or distanceBetweenTurtles(bat1,buttercup) < 10:
    score-=10
    setStart(bat1)
    
  # update score on screen
  scorestring ="Score: %s" % score
  scorekeeper.clear()
  scorekeeper.write(scorestring, None, "center", "16pt bold
```
The collision function also pushes the player's turtle backwards on the screen if they collide with an insect as a 'punishment'. Simultaneously, it hides the 'mosquitoes',
which gives the appearance of new food generating as the 'insect' hides from the position of collision and moves to a different random position on the screen.

While coding the obstacles, I had significant difficulty. My obstacles were initially rotating in one place but, for some reason, I could not replicate the same code
for the number of obstacles I wanted in the game. The code that *did not work* is given below:

```obstacle1 = turtle.Turtle()
obstacle1.shape("circle")
obstacle1.color("red")
obstacle1.left(90)
obstacle1.penup()
obstacle1.speed(0)
x = randint(-180, 180)
y = randint(-180, 180)
obstacle.goto(x, y)
while True:
  obstacle.forward(10)
  a = random.randrange(0, 4)
  if a == 0:              
   obstacle.left(90)
  elif a == 1:                     
    obstacle.right(90)
  elif a == 2:                      
    obstacle.forward(2)
  elif a == 3:                      
    obstacle.backward(2)

  if obstacle.pos() > Background.window_width() + eps:              # heads
        obstacle.left(90)
  elif obstacle.pos() < Background.window_width() + eps:                      # tails
        obstacle.right(90)
  elif obstacle.pos() < Background.window_height() + eps:                      # tails
        obstacle.down(90)
  elif obstacle.pos() < Background.window_height() + eps:                      # tails
        obstacle.up(90)
```


I ended up creating randomly walking turtles, which I am fairly happy with.

The code for the same is as follows:
```def randomWalk(t,w):
        if not isInScreen(w,t):
            t.left(180)
        else:
            throwCoin(t)
        t.forward(10)

def doubleRandom(t,u,x,w,timer,start,timer_cd):
    global bat1
    while time.time() - start <= TIME_LIMIT: #True: #not collide(t,u) and not collide(x,u) and not collide(x,t):
        randomWalk(t,w)
        # if collide(t,u) and collide(t,x):
        #   continue #break
        randomWalk(u,w)
        # if collide(t,u) and collide(x,u):
        #   continue #break
        randomWalk(x,w)
```


# Organization:
I have organized the game in a fairly self-explanatory manner. The names of my files are : main.py, level1.py, level2.py and level3.py. In the begnning, I only had two
files with one that setup the levels and the other being the menu but, with this organization, I was running into issues related to my code not executing in the order
that I wanted it to or some parts not executing at all. Dividing my code into different files and using global variables solved this problem.


# The Three Levels:
I have created three levels that give a gamified glimpse into the everyday experience of a bat. My bat character ‘tina’ starts her day in level 1 which is supposed to
emulate the experience of a bat exiting a cave. 

## Level 1:
The first level allows the user to click about and eat insects while avoiding the other turtles (which are supposed to be predatory birds that would prey on bats). I 
would have added images to my program if had more time but I really like the aesthetic created by different turtles walking across the screen with trails of different
colors. The different trails also add a layer of complexity for the player to navigate.

## Level 2:
For the second level, I manually drew a maze, like I had for my class extension project before. However, when I had my partner play the game, they quickly pointed out
the obvious bug where they were able to easily ‘walk over’ the boundaries of the maze. So I spent hours struggling to create code that would keep tina from moving if 
she collided with my maze's boundaries. I tried to recreate something similar to the code I found on a discussion board (linked below), which required recoding my maze. However, I was not able to
reproduce a working collision function in reference to the maze walls:
 https://stackoverflow.com/questions/69528771/python-turtle-touching-walls-of-maze
 
The code linked above uses closed polygons to detect if the turtle is within bounds.

My second option was to limit the number of steps tina would take in response to user input, therefore, deterring the user’s ability to fly across the screen and
completing the level - I used online discussion boards for help with the math. The resulting code is given below:

```def clicky(x, y):
  global bat2, insect, insect1, insect2, insect3, insect4, insect5, insect1a, insect2a, insect3a, insect4a, insect5a
  angle = math.atan2(y-bat2.pos()[1],x-bat2.pos()[0])
  dist = 10
  bat2.goto(bat2.pos()[0]+dist * math.cos(angle),bat2.pos()[1]+dist * math.sin(angle))
```

This ended up working out and I was fairly satisfied with it. So I added some colorful insects as treats for my player to eat as they navigate the
maze.

## Level 3:
This third level builds on the interface of the first with the premise of the game being largely the same - eat mosquitoes for a higher score and avoid surrounding
turtles for a penalty. However, I managed to increase the number of obstacles and the speed to challenge my player and keep them motivated to play further.

# Defining Screen Boundaries

At the start, my game objects would some times walk outside of the bounds of the screen, especially due to the random walking function so I decided to define margins.
Subequently, I positioned my game objects in reference to the measurements of the game window rather than hardcoding them.

```def setStart(t):
    tx = random.randrange(0,WINDOW_WIDTH/2,10)
    ty = random.randrange(0,WINDOW_HEIGHT/2,10)

    t.penup()
    t.goto(tx,ty)
    t.pendown()

def throwCoin(t):
    coin = random.randrange(0,2)

    if coin == 0:
        t.left(90)
    else:
        t.right(90)

def isInScreen(w,t):
    leftBound = MARGIN_FOR_INSCREEN
    rightBound = w.window_width() - MARGIN_FOR_INSCREEN
    bottomBound = MARGIN_FOR_INSCREEN
    topBound = w.window_height() - MARGIN_FOR_INSCREEN

    stillIn = True

    if t.pos()[0] < leftBound or t.pos()[0] > rightBound or t.pos()[1] < bottomBound or t.pos()[1] > topBound:
        stillIn = False
 ```
# Issues
One major issue I am facing is not being able to move my bat *after* the game transitions to a subsequent level. I tried fixing this by creating new bats for each level.
However, the functionality of the levels is fine if you run the program and select a level again. 

# Concluding Remarks

In the future, I would love to combine the maze with the walking turtles and create a pacman-style game with the 'enemies' inside the maze game. I would also like to
enable the user to also select a level with the keyboard. Currently, they only navigate the screen with the same. Coding just takes more time for me and, with such a
big project, it's very hard for me to keep track of different things efficiently and work in an organized manner in a short time.

I would love to add script in the console that further develops my character's story and incorporates some functionaity of a text-based adventure game, while still
keeping the output restricted to the screen. For example, my player might be able to choose between different game modes. One game mode could be the "Texas Freeze" which
would slow down the game, display a colder and more hostile environment in which my character cannot find food and is slowed down by the weather. This would be an imitation
of how bats face difficulty in flying during icy winters in Austin. I could also create 'spaces', such as an urban forest or a residential area which the user can
interact with in the console.

Moreover, I would like to figure out how to implement the closed polygons maze code I found online because of its greater efficiency and objectively neater aesthetic.
I would also like to rework the obstacles code I ended up deleting from the game to have different kinds of 'enemies'. Lastly, I want to see what the game would look like
with images and if I can somehow keep the colorful trails in the picturized version.

Still, I was able to pull together everything in the end and make use of new concepts that I had learned online. This was a happy reminder for me that the focus of
this course is on building vernacular, research skills and the ability to dissect the internal logic of given code - things that I certainly could not have done in
the beginning of this course. 


