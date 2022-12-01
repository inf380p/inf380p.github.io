---
 layout: posts
 author:greencouchpotato
 title: "Clicky turtle hack"
 ---
 
 # My Code link
 <iframe src="https://trinket.io/embed/python/42d87b75e7" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

 # My Reflection

 By far this is the toughest code that I've created. I initially tried to create a code from scratch and assign animations in the animations.py tab.

 However, I quickly realised this was gettng complicated and my code wasn't working. I was frustrated because I couldn't figure out what I was doing wrong.

 I then took the sample code provided in the assignement and started tweaking the values and functions to understand it fully and how different functions were called. Later, I've created a background to make the screen attractive and coded 'snowflakes'. The user will be able to create snow on screen with the click of their mouse.


 So I was able to learn the onclick function. 

 ```
 def clicky (x, y):
   tina.hideturtle()
   tina.speed(100)
   tina.penup()
   tina.goto(x,y)
   tina.pendown()
   tina.color ("white")
   tina.fill(True)
   tina.circle (10)
   tina.fill (False)

 myscreen.onclick(clicky)
 ```


 #My Challenges

 I'm yet to figure out how to make the turtle react to keyboard commands. I'll try to improve my existing code to make this work. 
