---
layout: post
author: jpmartinezutexas
title: "Project Update -Interface Draft"
---

# What is my project?
My project is a turtle game, similar to galaga and Ikaruga. So far, I have created player controls and drafted an interface on Figma. 

You can view my interface here. 

https://www.figma.com/file/6AjJWT6jyUkUkQC1pcP81g/Galaga-like-game-Wireframe-drawing?node-id=0%3A1&t=nNf5nzPxXDIQVLKH-1 

I am still working on implementing the actual file, figma says that there is an embed feature, but I haven't figured it out yet. 

# Here is my project so far!
<iframe src="https://trinket.io/embed/python/93ae9c7822" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

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

# How on track am I? 
Admittedly, I did not get much done this past week due to having two other projects due Wednesday which took a majority of the focus of my time.

# What will I work on this week?
I will implement cerating enemies, letting the player and enemies shoot. Those are my goals. I will have a lot of time this week to complete these tasks over the break.
