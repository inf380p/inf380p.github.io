---
layout: post
author: jpmartinezutexas
title: "Project Update -Interface Draft"
---

# What is my project?
My project is a turtle game, similar to galaga and Ikaruga.

You can view my interface here. 

https://www.figma.com/file/6AjJWT6jyUkUkQC1pcP81g/Galaga-like-game-Wireframe-drawing?node-id=0%3A1&t=nNf5nzPxXDIQVLKH-1 

I am still working on implementing the actual file, figma says that there is an embed feature, but I haven't figured it out yet. 

# Here is my project so far!
<iframe src="https://trinket.io/embed/python/93ae9c7822" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# How on track am I? 
I thought I would be able to get a lot done during my break, but due to unexpected events, I was hardly able to work on my project. What is really unfortunate is
that this is my second to last semester, so I have really been stressing about finding a capstone project, or I won't be able to graduate. I also have had 
projects that were due Wednesday (yesterday) that were the final projects for my other two classes, so I had to do them first. They were also group projects, and my group was counting on me.
With 2 projects and finding a capstone, I unfortuntately have been swamped beyond belief. 

However, I am not giving up! I now have a capstone (almost completely) secured,
both other classes down, and I will have a week to put all of my academic focus into this project. 

# Possible scope changes
I may remove the ikaruga inspired part about changing states, the product MUST have the player able to shoot at enemies, be able to be hit by enemies, and have 3 levels.
However, As of 9:30 pm last night, I am completely done with 2/3 of my classes, this being my last one. Thus, I intend to go really hard on this project in the next week until the 8th.
This is my scope by day: 
12/1: Finish creating enemies, bullets for enemies/players
12/2: Make score system
12/3: Make level end states, make 3 levels with more enemies on each
12/4: Make simple sprites for characters, (8 or 16 bit) and implement the photos into my python project for player/enemies.
12/5: Make blue/orange state
12/6-12-8: Debugging, anything else that is needed. 

# Some sample code 
```python
# Tell the program which functions go with which keys, for purpose of using WASD inputs.
myscreen.onkey(go_left, 'a')
myscreen.onkey(go_right, 'd')
myscreen.onkey(go_forward, 'w')
myscreen.onkey(go_backward, 's')
```

# What are the steps I need to take?
Here are the tasks I need to do, and  this will be updated as I move further along with the project.
```python
# X Move the turtle player with WASD, up down left and right
# - When you press space, snoot a block that continuously moves up
# - If the square collides with an enemy, it will destroy it and give the player 20 points.
# - If enemy collides with player, both will be destroyed and the player loses 1 health.
# - Give player health, 3 may edit later.
# - Populate screen with enemies on a semi random basis
# - Make 3 levels. Easy, medium, boss (boss may be a stretch but we shall see)
# - Create Enemy health
# - Create Player Health
# - Create Enemy AI - they try and follow player
# - Create player states - blue and orange
# - While blue, cannot be damaged by orange
# - While orange, cannot be damaged by blue. 
# - Enemies shoot bullets of blue or orange depedning on if enemy is blue or orange, those when colliding will give player -1 health as well.
# - Create User Interface
# - Health
# - Score
# - State (blue or orange, replacing the light/dark of ikaruga)
# - Level
# - Create and import background image
# - Create and import player image
# - Create and import enemy image
# - Enemy Image 2 
# - Enemy Image 3
# - Boss Image
# - Blue Bullet Image
# - Orange Bullet Image
# - Make sure to follow the needed parts of final
# - At least 1 external data file
# - Dictionaries
# - Custom Modules
# - definite for loops
# - Custom Functions
# - Python 3 or pygame trinket
# - Readable code
# - well commented
# - well organized
# - idiomatic
# - error-free
# - largely bug free
```
