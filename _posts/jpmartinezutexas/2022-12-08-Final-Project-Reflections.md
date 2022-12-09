---
layout: post
author: jpmartinezutexas
title: "Final Project Complete"
---

# What is my project?
My project is a turtle game, similar to galaga and Ikaruga. If you have not played Ikaruga the short and simple
is that it is a top down arcade shooter and you have two modes, light and dark. While you are light, you cannot be damaged by anything light.
While you are dark, you cannot be damaged by anything that’s dark. For my game, I did something similar, but I ended up using red and blue instead of light and dark, because I thought it 
would be easier to see with the python turtle color schemes, especially since I had a space background. 

I originally was going to do a text based adventure, but I decided that I liked the graphical turtles, and was in the mood to make something fast paced, like an arcade shooter. An arcade shooter was also the first game I made 
in Game Maker Language (GML) so I thought it would be a good idea to do something similar in python. I was able to map out my tasks with things like collision because I had dealt with those kind of tasks before in GML.

You can view my initial interface here draft I did on figma here. 

https://www.figma.com/file/6AjJWT6jyUkUkQC1pcP81g/Galaga-like-game-Wireframe-drawing?node-id=0%3A1&t=nNf5nzPxXDIQVLKH-1 

First interface here - https://trinket.io/embed/python/93ae9c7822

# Here is my finished project!
<iframe src="https://trinket.io/embed/python/f17d5e225a" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Admittedly, it is not as done as I was hoping for it to be. Unfortunately, there were many times when I was trying to make something work, that seemeed like it should work, but no matter what I did, it wouldn't do what I wanted at some points. 

If you would like to see my progress, I have attached all of the relevant versions of my project. Instead of embedding them, because that would be a lot. I will simply link them. 
A lot of these udpates are kind of inconsequential, it was mainly me doing it for version control. Regardless, I think it is good to show them.

This is the first interface draft I had - https://trinket.io/embed/python/93ae9c7822

This is a meaty update I had, a v2 - https://trinket.io/library/trinkets/8ef04e84c4

https://trinket.io/library/trinkets/a531183c1e v3

https://trinket.io/library/trinkets/26c40e9e6b v4

https://trinket.io/library/trinkets/2d7e7e94a0 v5

https://trinket.io/library/trinkets/fedcd46f03 v6

https://trinket.io/library/trinkets/9c90761e05 v7 

https://trinket.io/library/trinkets/75516ea571 v8 

https://trinket.io/library/trinkets/f17d5e225a v9 - final, the one at the top (final as of 12/8/22 anyway)! 

# Steps/Task List

Although I did not manage to get everything working, I would like to go in-detail about my code, because a lot of it I thought I was doing the right thing, but my results disagreed with me. 
But first, I would like to talk about my task list - 

Task list I made (I ende up changing orange to rec, just a stylistic choice) Here, as a sort of TL:DR to my reflection, I have put dash marks explaining my progress on all
of these tasks, and what I had trouble on/what was intended. 

X is done,

? is attempted, 

"-" is left out due to scope reasons (I would like to continue this project still!)
```python
# X Move the turtle player with WASD, up down left and right
# X When you press space, snoot a block that continuously moves up - Done, but not 
# ? If the square collides with an enemy, it will destroy it and give the player 20 points. - Adjusted points for testing, was not able to get it to destroy
# - If enemy collides with player, both will be destroyed and the player loses 1 health.
# X Give player health, 3 may edit later. - Gave 3 lives
# - Populate screen with enemies on a semi random basis
# ? Make 3 levels. Easy, medium, boss (boss may be a stretch but we shall see) - attempted, but not working fully
# - Create Enemy health 
# X Create Player Health - 3 
# ? Create Enemy AI - they try and follow player - attempted, not finished, (Commented out)
# X Create player states - blue and orange - changed to red
# - While blue, cannot be damaged by orange - Was unable to get to the damage part
# - While orange, cannot be damaged by blue. - see aboce 
# - Enemies shoot bullets of blue or orange depedning on if enemy is blue or orange, those when colliding will give player -1 health as well. - unable to get to this part
# X Create User Interface - done, used dictionaries - Done 
# ? Health - attempted but not working fully
# ? Score - Attempted but not working fully
# X State (blue or orange, replacing the light/dark of ikaruga) - red not orange, damage doesnt work
# X Level - Attempted but not working properly
# X Create and import background image - Done!
# - Create and import player image (not needed, used turtles)
# - Create and import enemy image (not needed, used turtles)
# - Enemy Image 2 (not needed)
# - Enemy Image 3 (not needed)
# - Boss Image - didnt get to :(
# X Blue Bullet Image
# X Red Bullet Image - was unable to get this to work, not sure why.
# X Make sure to follow the needed parts of final
# X At least 1 external data file - intro.py, UI.py, lvltimer.py, dictionary.py
# X Dictionaries - settings = {"level": 1, "lives": 3, "score": 0}
# X Custom Modules - intro.py, UI.py, lvltimer.py, dictionary.py, I imported lots from each.
# X definite for loops - my star I drew with a for loop
# X Custom Functions - lots of these, esp. player functions like changing color from red/blue
# X Python 3 or pygame trinket - #!/bin/python3
# X Readable code - I did my best to keep my code readable, with proper spacing. 
# X well commented - I explain a lot of what I was trying to do 
# X well organized - I tried to do things like keep player components together, bullet components together. 
# - idiomatic
# ? error-free - The program runs and does not crash in its final state
# > largely bug free - Unfortunately there wre bugs that I was not able to solve at this point in time. 
# X Have a graphical user interface, responding to key and click events - I did with onkey events, it explains how to change colors to the player. 
# X Have a constantly available help dialog. This can take many forms but should allow the user to learn what they can do in the program at any time. - The player always can see the controls 
# X Display information about the program’s state such as score or level - This is always on display
# X Extend a custom Turtle Class - init - I did this with the lvltimer and the UI python.
# X Have a ‘win’ screen - I have this - main.py line 83
# X Have an iterative interface. That is, the user should be able to perform any number of supported actions (such as playing the game over and over)  - attempt at a restart
# X Use one or more custom images - The background is custom pixel art of space that I made myself. 
```

I would like to thank the resources I used.

https://docs.python.org/3/library/turtle.html#module-turtle - The turtle module came in very handy for my project, it acted like a turtle encyclopedia, with me able to quickly ctrl-f things I needed a refresher on. 

https://www.w3schools.com/python/default.asp - I used this when I was learning HTML/CSS/JavaScript, and it can be helpful for python too. 

https://runestone.academy/ns/books/published/inf380p2022/dictionaries/dictionaries1.html - Runestone academy in general, it was a helpful resource.

https://inf380p.github.io/reading/how-to/interface.html - This tutorial helped me a lot when I was first making a real interface, thanks professor! 

https://inf380p.github.io/reading/how-to/turtle.html - Especially helpful for using images in turtle. 

# Extended Reflection and code examples
This project was hard. Like I said in my prior reflections, due to my other class finals being due before this class (and finals week) I had to take care of those classes first, as they were also group projects, and I felt that I needed to give it all my all in those classes. I also had to have a capstone project secured to graduate by the 5th (which I did). 
Basically, I ended up working on much of this in the final week of the project. I really wish I had more time to do this project, I know that I had ample time, but with the way that due dates turned out this year, I had trouble managing my time. 

Regardless, in this final week, I put a lot of work into this project, and really made something that I think looks pretty cool! Unfortunately, not all of it works (as you have noticed in my reflection), which is why I would like to go over a lot of the code, and explain my reasoning for how I coded it. 
Despite not having a lot of time, I tried my best to pace myself, taking mental breaks when I needed to. For me, stepping away from the code for a while is always a good way for me to get a fresh perspective on problems, and although it isn't a surefire way to solve bugs, it is good for my mentality to lay fresh eyes on the problem. 
Another thing I found useful was cleaning as you go, even if it was just erasing extra spaces, or commenting out things like they were sticky notes for a great story I was writing. 

Alright, let's get into the code, I'm going to explain some of the problems I ran into, and how I am still confused about them. 

This first one has to do with me creating collision between the enemies and the bullet the player creates. 
```python
#bullet and enemy collision

#def eposition():
#  enemy.position()
  
#def bposition():
#  bullet.position()
  
#if eposition() == bposition(): #when the bullet and the enemy are at the same place, that will trigger collision -didn't work
   #bullet.color("black")
   #bullet.hideturtle()
   #enemy.hideturtle()
```
This was my first of many attempts at creating collision. Here, what I wanted to do was define the enemy position and the bullet position, and use an if - then statement to have them check if 
those values were equal to each other, it would trigger the collision. The bullet would turn black (for testing, I would also hide it), and the enemy would be hidden as well. 
Unfortunately, none of these things happened, so I moved onto another attempt. 

More collision attempts
```python
# if enemy.xcor() == bullet.xcor() and enemy.ycor() == bullet.ycor():
#   bullet.hideturtle() 
#   bullet.color("black")
```
This was another attempt I had, using an if/and then statement. My logic here was similar to the first time, except that I was manually checking the posotions.
If the enemy's x cordinate matched the bullets x cordinate, AND the y cordinates matched up, I wanted it to hide the bullet at least, to see if it would work. Unfortunately it did not, but I didn't move on just yet. 
```python
while enemy.xcor() == bullet.xcor() and enemy.ycor() == bullet.ycor():
  #bullet.color("black")
  bullet.hideturtle()
  settings["score"] += 1
else:
  bullet.showturtle()
```
This time, I tried using a while/else statement, but to no avail.

I also had a significant amount of trouble with updating my score. I have a dictionary in a separate python file which I transfered over, and it was able to display on the UI. 
```python
settings = {"level": 1, "lives": 3, "score": 0}
```
This would count the player level, player lives, and the player score. The player loses lives by coming into contact with the enemies of opposite colors.
Once the player would hit a certain score threshold, the level would increase, and more enemies would pop up. This way the player could play non-stop.

I also added a function to restart the game with p, using an onkeypress, which I had good results with when switching
colors and other player inputs. Unfortunately, it did not work, een though I wrote them the same. I am still confused about this one. 

```python
def restart():
  #time.sleep(100) # was going to use this for pause 
  settings["level"] == 1 #makes level back to 1
  settings["score"] == 0 #makes score back to 0 
  #write someething to make all the enemies come back

#lots of space in between these, as I wanted to keep the onkey presses altogether.

myscreen.onkey(go_left, 'a')
myscreen.onkey(go_right, 'd')
myscreen.onkey(go_forward, 'w')
myscreen.onkey(go_backward, 's')
myscreen.onkey(fire, "space")
myscreen.onkey(change_blue, 'e')
myscreen.onkey(change_red, 'q')
#restart the game
myscreen.onkey(restart, 'p')
```
I also was not able to get the score to increase, I even went so far as to put a score increase function in def change_blue():, which I knew for a fact worked as I could see the player change colors. 

```python
def change_blue():
  player.color("blue")
  settings["score"] += 1
```

I feel that it must be something simple that I am missing. This is a big problem I have had with coding, just missing something simple. Unfortunately, I didn't even get any 
errors in the console, it just did not change or react, so it wasn't like I was able to be pointed to an exact line of code that was messing things up. Perhaps I was just building it wrong. 
Even so, I wanted to show my thought process. A lot of the times, I felt that I had the right idea, but was just missing execution. 

I would also like to talk about some triumphs in my code. I think the project looks really good, and the ability to switch between red/blue is pretty snappy. The dictionary is integrated into the UI, and the player is able to fire bullets at enemies. 
I was also happy to be able to easily import things from other python files, which I found especially helpful for organizing code. I realize that it may not be extremely optimal to have an entire .py file dedicated to the dictionary, but it meant that I would have a dedicataed place to put more dictionaries in the future.
I also just really like seeing them as tabs, instead of having to sift through hundreds of lines of code on the same document. Even with ctrl f, it can be easier just to have the tabs. 

# Wrapping up 

Although the project was tough, I feel like I learned a lot, and I am proud of what I was able to get done. I was able to use lots of things we learned in class like dictionaries and loops. Things like making the star, or changing the color of the turtle, I found came easily to me, which I am really happy to say.
So even though not everything was right, I felt that I still learned a lot about applying knowledge I've learned over the semester in this project. 

Although it can sometimes be a frustrating process, coding can also be really satisfying when I get something right, especially after trying for so long. For instance, 
even seeing my turtle change from red to blue, and shooting out a bullet on a background I created just makes me happy. 

I'd really like to improve this project, but I will do so on another trinket, so as to show my work at the time of the due date on V9.

For future reference, this is the trinket I will be working on to fix up this project in the future. 
<iframe src="https://trinket.io/embed/python/105504580c" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Thank you for an awesome class everyone! I appreciate the support of my classmates and the professor, and I hope to see you all some time soon!
