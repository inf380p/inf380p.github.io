---
layout: post
author: hyotester
title: "Hyo's Project Update Post"
---

# Old plan

My initial idea for the final project to build a game to find your route in the hospital. I spent time exploring pathfinding code and practicing code through the existing frame: How to Make a Turtle Maze Game. Based on this experience, I’ve learend codes to achieve my initial milestones: 

## Initial milestone

- [x] Drawing or import hospital map (images) at the right scale 
- [x] Calculate the speed and direction to search for current place / follow right direction / arrive final destination


<iframe src="https://trinket.io/embed/python/3779b6ba4f" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


# New modifications 

I just realized one thing while learning and focusing only on pathfinding. How can the visitor select the desired location and recommend a fast route? Also, I wanted to add fun factor and user engagement into the game. Therefore, I will modify and add more steps.First of all, I will provide “instruction” that Clicks or keypresses(Listen for at least the 4 arrow keys and one more key to control the red ball’s position and one other aspect of its state) to move the red ball until it reaches the destination marked by a yellow map icon.
After arriving at the final destination, the system lets the user know how long it takes to reach the destination. I will provide a list of departments using list functions that I’ve learned during class.

User flow

![flow](https://user-images.githubusercontent.com/89994799/204352880-0713c278-ee32-432e-9443-52e659fe50d1.png)


# My current process 

Completed turtle maze challenge to calculate the speed and direction for current place
Completed list of options for the interface location
<iframe src="https://trinket.io/embed/python/798ade83c8" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# What I intend to accomplish before I turn in your project:
-Need to build functions:
- [ ] Clicks or keypresses(Listen for at least the 4 arrow keys and one more key to control the red ball’s position and one other aspect of its state)
- [ ] Move the red ball until it reaches the destination marked by a yellow map icon
- [ ] Count time to arrive final destination
- [ ] Provide view solution

