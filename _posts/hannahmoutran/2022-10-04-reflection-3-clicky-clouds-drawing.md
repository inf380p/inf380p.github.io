---
layout: post
author: hannahmoutran
title: "Hannah Moutran's Third Reflection - Clicky Clouds Drawing"
---
# Drawing the Sky 

For the Clicky Turtlehack assignment, I created a program where the user clicks with their mouse to draw the clouds, and can change the background color, which represents the sky, using their arrow keys and space bar on their keyboard.  

My first thought was that I would draw clouds, and then hide a rainbow inside of them, so that when the user clicked, some of the clouds would remain white and others would change color, one would be red, another orange, another yellow, etc.  Something encouraging would pop up at the end when they had created a beautiful rainbow out of the clouds.  I wanted to make the clouds into screen objects, like buttons, so that when you clicked on them, there would be a corresponding response from the program.  That was proving very complicated, so I switched gears and decided to create a program that would let the user make their own cloud arrangement.  

I’m glad I did, because it’s very nice and relaxing to make the clouds in the sky.  So, how to do this?  Well, it was important that the user knows how to work the program, so the first step was to just very simply write out how to use the mouse and keyboard to draw the sky.  This was also the last step, of course, because I had to keep updating it to reflect the updates to the program.  I made the text white, as the backgrounds were always colorful, and also it matched the clouds.  Here are the directions for the user, in the code: 

```
sally.color("white")
  sally.penup()
  sally.goto(0,-100)
  sally.write("Click to make clouds", None, "center", "12pt bold")
  sally.penup()
  sally.goto(0,-130)
  sally.write("Use your arrow keys to change the color of the sky", None, "center", "12pt bold")
  sally.penup()
  sally.goto(0,-160)
  sally.write("Press the space bar to go back to light blue", None, "center", "12pt bold")

```

The next step was making the `clouds` function, which needed x and y for arguments, because wherever the user clicks, those coordinates are where the cloud will begin to be drawn.  I put that over in the animations tab, and called it into the main tab at the top of the code: `from animations import clouds`.  Here’s the cloud function: 

```
def clouds (x,y):
  sally.penup ()
  sally.goto (x,y)
  sally.pendown
  sally.fill (True)
  sally.color ("white")
  sally.circle (15) 
  sally.penup ()
  sally.forward (18) 
  sally.pendown ()
  sally.circle (20) 
  sally.penup ()
  sally.forward (18) 
  sally.pendown ()
  sally.circle (15) 
  sally.fill (False)
  sally.penup ()

```
Here is the function in the main tab that called the cloud function and made it appear for the user upon clicking in the console:

```

def clicky(x, y):
  clouds (x,y)

```
 
I set up the screen in the animations tab, as well, with a light blue color, and then called that to the main tab.  In order for the user to get back to that original, light blue screen setup, I used this code: 

```

def back_to_sky_blue (): 
  tina.clear ()
  setup(myscreen)

myscreen.onkey (back_to_sky_blue, 'space')


```

And to change the screen background to different colors (yellow, pink, dark blue, and purple) I used the following code: 

```
myscreen.onclick(clicky)

# Functions called by keyboard clicks 
def yellow_sky():
  myscreen.bgcolor ("#F1C40F")
  
def purple_sky():
  myscreen.bgcolor ("#D7BDE2")
  
def dark_blue_sky():
  myscreen.bgcolor ("#5499C7")
  
def pink_sky():
  myscreen.bgcolor ("#F1948A")
  
def back_to_sky_blue (): 
  tina.clear ()
  setup(myscreen)
  
# onclick function keys
myscreen.onkey(yellow_sky, 'left')
myscreen.onkey(purple_sky, 'right')
myscreen.onkey(dark_blue_sky, 'up')
myscreen.onkey(pink_sky, 'down')
myscreen.onkey (back_to_sky_blue, 'space')

```

And, of course, for the screen to ‘hear’ that, I needed this piece of code: 

```
myscreen.listen()

```
And that’s that!  A pretty simple week, and I’m very happy with this little drawing program! 

# Full trinket below: 
<iframe src="https://trinket.io/embed/python/7c1ddbabe6" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

