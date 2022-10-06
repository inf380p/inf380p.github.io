---
layout: post
author: RosalindBradshaw
title: "Rosalind Bradshaw's Clicky Turtlehack"
---

For this assignment I wanted to take on the challenge of creating a game to find the hidden treasure. In my original vision for this game I wanted to give the
players a number of different environments they could choose from based on where they clicked on the screen, each environment would have a different background
color and treasure type.

The first thing I tackled was how to get code to pul from a separate module. I knew this would be a challenge because I haven't done any thing that involved
creating my own modules. I took a long time fussing around with the code, using trial and error, and looking at examples from the class to figure out exactly how to get the modules
working and make the code communicate effectively with itself, but I eventually got it figured out.

The next step was changing background colors based on the mouse click. We've seen examples of this in class, but not with more than two colors,
and I knew I wanted at least four. This was my first time playing with clicky turtles, my previous codes have always involved extensive keyboard inputs. I tried
looking in the textbook and, while it's a fantastic resource for practicing coding, it is significantly less useful when writing new code with specific
synatx. To make my screen change colors I used this system:

```
if (x <= 0) and (y >= 0):
    beach()
  elif (x >= 0) and (y >= 0):
    grass()
  elif (x <= 0 ) and (y <= 0):
    forest()
  else:
    snow()
```

This allowed me to break the turtle screen into four quadrants and change the color based on which quadrant the click occured.

The next step was figuring out how to make the search function work. For this, I had to import the `random` function to enable my turtle to go to a random
set of `x, y` coordinates. This ended up being the biggest challenge for me, not to get the turtle to go to a random place, but how to get a second turtle to
respond one way when in the right area, and a different way in the wrong area. I took several hours messing around with the code, looking on-line, and mulling
over the entire issue. I knew there had to be a way, I just wasn't seeing it. Eventually, I realized that the program was waiting for me to click on the exact
pixel coordinate, which is an incredibly tiny spot. To broaden that area out, I realized I had to create a range of options that would count as "good". And
that looks like this:
```
if (rand_x <= x <= target_x) and (rand_y <= y <= target_y):
```
The only oversight for this system is that, instead of creating the area centered on the turtle, ahead and above it. Which isn't a terrible thing, but it did
take me a while to figure out where was the correct area to click to get the win condition to trigger. I also found out that the turtle can choose a random
number so close to the edge of the game that the correct target area can be mostly off the screen, this required a bit of tweaking to the random numbers to
keep them more centered on the screen.

The next step was integrating them both into the same program. This ended up being a lot messier than I wanted it to be.

<iframe src="https://trinket.io/embed/python/03105492f5" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

As you can see from the finished product, the game changes colors based on the first set of clicks, and then has to wait for a user input to begin the search
portion of the game. In an ideal code I would have liked to have it clear the screen after the environment was chosen and then go to the search portion,
but this will be a potential hurdle for a future day.

Other future improvements might be to add more environmental details to the game, or add in a function that tells the player when they are hotter or colder from
the target. The most amusing part I found in this code was, if I click too much when the program is trying to draw the treasure chest, the turtle scribbles all
over the screen, which is highly amusing to me.
