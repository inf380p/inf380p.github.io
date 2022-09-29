---
layout: post
author: alm7468
title: April's Focused Reflection
---
Pre-Click Addition:
<iframe src="https://trinket.io/embed/python/ae82180497" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>  

Goal: to add a click response to confirm the user's meal order. The current response is accepted through  typing Y or N.

Big Picture Plan: I’ll need to set up a few new functions. I’ll have to decide where on the screen my yes and no would go, plot them, then use those coordinates as parameters. So while the user is clicking the word “Yes” the program is just responding to the location of the click on the screen, not a button. Though I will likely build a rectangle with the word in it to create visual boundaries for the clicks (She did not).

hmmm where to start…
After asking the user to “Is this correct?”, I think I’ll put yes and no on opposite sides of the y-axis so that I can use x < 0 as Yes and x > 0 as No. 

Now I have to figure out how to write the functions properly.  
(But first I’ll make dinner so that I don’t tap out quickly.)  
(ok actually I ate and I just want to shower and go to bed. I’ll try to build the code tomorrow.)  
Note to self: I’m working in Copy of Copy of TakeYourOrder trinket.

I’m looking at next week’s click related function code from the materials section of our class website. I'm reading the code to see if there's something I can use in my code.

I’m adding ```screen.onclick()``` function method to call a ```clicky()``` function. Since the code of responses to Yes and No already existed, it made this preocess much easier than starting from scratch. I turned Yes to
```python
def clicky(x, y):
  if x < 0:
    tina.clear()
    tina.color("red")
    tina.speed(5)
    tina.goto(-150,150)
    tina.showturtle()
    tina.write("NOW", None, None, "50pt bold")
    tina.goto(30,120)
    tina.write("GIVE", None, None, "30pt bold")
    tina.goto(0,50)
    tina.write("ME", None, None, "40pt bold")
    tina.goto(-20,-30)
    tina.write("YOUR", None, "left", "50pt bold")
    tina.goto(-20,-130)
    tina.write("MONEY!", None, "center", "60pt bold")
    tina.goto(0,-170)
```

OMG IT WORKED.
At first, I forgot to put "clicky" in the parentheses of ```screen.onclick(clicky)```.  

hmmmm, it’s doing something weird as a response to clicking No. The text is running off the screen even though the alignment is centered.
Solution: I needed to add a ```.goto(x,y)``` prior to ```.write()``` to the “else:” because the text is coming from the turtle, and the last location of the turtle was where the text “No” from ```def confirm()``` is located on the screen.
```python
else:
    tina.clear()
    tina.showturtle()
    tina.goto(0,-50)
    tina.write("I'm sorry, let's start over", None, "center", "20pt bold")
    tina.goto(0,-130)
    take_order()
    confirm_order()
```
Maybe I've gotten a little TOO dependent on the secondary module (tab). Do I have enough code exposed in Main.py?
AFTER:
<iframe src="https://trinket.io/embed/python/8b4b4ac77e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

