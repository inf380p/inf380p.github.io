---
layout: post
author: nemothefish260
title: "Project Update - Interface Draft"
---

My current interface include my ‘bat character’, an insect that reappears on a different part of the screen on collision with the bat hence making it seem as if I have
multiple insects that the character can catch, and a few obstacles (i.e. predatory eagles). My obstacles are also moving randomly now across the screen, as opposed to
last time when they were static and didn’t interrupt gameplay. I was also able to add a working scorekeeper on screen.

I think my current game design is not innovative enough and I do not have the ability to realize the ‘moving scene’ interface I had imagined before. I have compromised
by making the rewards and obstacles move in the small space I currently have instead. I might appreciate ideas that I can realistically include to make the game more
entertaining.

In the next week, I have the following milestones:

Create a ‘boundary’ to keep my game objects from leaving the screen

Add images to my game objects to create avatars and background

Add catchphrases that print on screen whenever other objects collide with my character

Add a timer on screen

Add two other levels to my game


Below is a snapshot of my code as well as a link to my project:

(I am proud of being able to write code that moves my obstacles randomly across the screen.)

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


Link: 

https://trinket.io/python/755fb8fdce




