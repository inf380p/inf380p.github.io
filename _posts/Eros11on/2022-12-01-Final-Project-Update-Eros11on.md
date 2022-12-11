---
layout: post
author: Eros11on
title: "Zheng Zhong's Final Project Update"
---

**So far, I think I've made a lot of progress on top of what I did last week. I'm also gradually completing my projects according to the schedule and the list of milestones I set up earlier.**

## General list of milestones
-  [ ]  At least one external data file<br />
 - [ ]  Dictionaries<br />
 - [ ]  Custom modules<br />
 - [X]  Definite `(for)` loops<br />
 - [X]  Custom functions<br />
 - [X]  Have a graphical interface, responding to click events<br />
 - [X]  Consistently available help dialog <br />
 - [X]  Display information about programs state<br />
 - [X]  Have at least 3 levels<br />
 - [X]  Extend a custom turtle class<br />
 - [X]  Have a ‘win’ screen<br />
 - [ ]  Have an iterative interface<br />
 - [ ]  Use on or more custom images<br />
 
 ## List of milestones that I have achieved last week
 -  [X]  Improved game interface, added the function of dispalying scores<br />
 - [X]  Added block move, drop function<br />
 - [X]  Added the function of eliminate a row and get the score<br />
 - [X]  Added the function of increasing the score and difficulty when a row is completed<br />
 - [X] Added the function of changing directions of block, pausing block and changing shapes of block  <br />

**This is my current program**
<iframe src="https://trinket.io/embed/pygame/75f8b69ce2" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Reflection

- **When I first designed the rotate block feature, I didn't have a clue at first. Because I was able to move the block up, down, left, and right very smoothly by simply increasing or decreasing the coordinates of the block. But when designing the rotation, I couldn't simply add or subtract coordinates. After reviewing a lot of materials, I found that I could implement the following code, which immediately opened my mind.
```(active_block_index + 1) % len(active_block.tiles)```**
- **I think my milestones are ambitious enough. Last week I not only completed the original level 1, but also had great success in attempting level 2.**
- **I am able to keep to my plan. However, I encountered some unforeseen problems in completing my intended plan. I initially thought the function of restarting the game was too simple, thinking that I could just set up a loop, but after I finished the other functions, I found that I couldn't get the restart to work. This required me to re-examine the entire code. Also my code was redundant in a main file, and I needed to reorganize my code into several modules.**


## What to do next
 -  [ ]  Create one external data file and use dictionaries<br />
 - [ ]  Add the function of restart the game<br />
 - [ ]  Custom modules and reorganize codes<br />
 - [ ]  Add one image<br />
 - [ ] Test whole game  <br />


<div align=center><img width=300 hight=300 src="https://www.utexas.edu/sites/all/themes/utexas/img/general/logo.svg"/></div>
