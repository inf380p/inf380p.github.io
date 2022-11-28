---
layout: post
author: inf380pcoder
title: "Inf380pcoder's Clicky Turtle and Reflection"
---



I found this week’s assignment to be a little bit challenging because I had to wrap my brain around having to think about three tabs of code with three different functions. It was hard for me to conceptualize how to do multiple things within the program, such as creating the helper functions, and calling them to the other two tabs. Or, creating functions in the animations tab and being able to call them in the main tab. It was a bit fuzzy to me when I first went through and watched the tutorial videos. 

With more practice, though, I think it’s making more sense to me. You just have to be careful because if you make a change to one tab you have to make sure it’s also correct in the other tabs. I got several error messages as I tried changing things between tabs. I also had different turtles. So if you try to call one of them in a tab where it isn’t defined, it also gives you an error message. I can see why setting up a program this way can be useful for certain purposes, it just requires you to make sure you’re carefully keeping track of your code as you go. 

I was initially trying to think of what to create for this assignment. I created a scene that allowed the user click the screen or a button to change the background color, which changed the scene to look like different times of day. I wish I could have changed other parts of the screen along with the background, like changing the sun to a moon by clicking, but I don't know if that's possible in turtle. I then allowed the user to move the turtle around to draw something else in the scene. After doing some reading, I figured out that you can do a draw function using `ondrag`. However, I couldn’t figure out how to input `ondrag` functions in my program, since I had already input `onclick`. This is a much easier way to use the turtle to draw compared to the one I had in my program, using the key functions. I might try to use this on another program in the future. 

**Here is the drawing function that I created:**

 ```python
from turtle import *
shape("turtle")
color("blue")
speed(10)
pensize(3)
 
def draw(x,y):
 
    ondrag(None)
    goto(x, y)
    ondrag(draw)
 
ondrag(draw)
 
mainloop()
```

**Here is the clicky trinket that I created:**

<iframe src="https://trinket.io/embed/python/6459a413a5" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
