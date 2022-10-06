---
layout: post
author: iLiekatz
title: Prison Break!
---

Here is my prison break program:
<iframe src="https://trinket.io/embed/python/88bde472f3" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

For this assignment I struggled on where to start. I feel like I lack creativity with what I can program at this point of my learning. Learning the language has been a challenge for me to fully wrap my head around, so when given a prompt to create something unique I have a hard time putting aside my technical struggles. I had to do some outside research to spark inspiration on what I could program for this assignment. And that's how I came up with this attempt at programming a simple click game that was sort of like a treasure hunt game.

The idea for this program is that Bob, Tina the Turtles owner has been locked up in jail. She is attempting to bust him out. There are 5 locks, but only one works. The user is to click around and help Tina find the right lock to free Bob. 

I had many different problems along the way, some that I was able to solve and some that have been left unsolved. The first problem I was faced with was creating the my clicky() function shown below.

```
tina = turtle.Turtle()
tina.shape("turtle")
myscreen = turtle.Screen()
setup(myscreen)

def clicky(x,y):
  tina.penup()
  tina.goto(x,y)
  tina.speed(5)
  ```

This was a fun problem for me to solve. I understood what I needed to do, and possibly how I would go about doing it. It took a couple trial and errors. After running my code a few times, I realized I had been leaving out setting up my screen. Small errors like that kept coming to light, and I was able to troubleshoot my way to creating a clicky function. I feel like I created a simple function, but by keeping it simple this time I was better able to understand the process. I would like to do something outside of the box as the professor suggests to challenge myself.

The next problem I had is still unsolved. The primary goal of this entire program was to have a conditional when Tina reaches a certain (x,y), and then the jail would go away and Bob’s frown would turn to a smile. I am struggling with conditionals in application. As I have worked my way through the textbook, I understand the concepts. But I have yet to put it to use. I think this is something that I need to work on with other coders. When left to my own trial and error, I have not been able to work through it. 

For now, I have used lots of comments at the bottom of my program to track my thoughts as I work to solve this problem. It is something I hope to tackle over the coming weekend for fun!
