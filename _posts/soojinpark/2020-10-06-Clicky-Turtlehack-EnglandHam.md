---
layout: post
author: EnglandHam
title: "Soojin's first Clicky Turtle Test 1"
---

## Reflection 
In the past, I used to feel overwhelmed when there were conditions within functions and branches within branches. I am a visual person so in my head, I try to draw a mental model of nesting branches and functions but fail to picture them. So I would try to write simplest codes that make more literal sense to me while compromising my ability to write codes more efficiently. With this homework, the past turtle videos, and the textbook, I am now able to slowly adjust myself to how programmers think and visualize helper functions and importing ".py" tabs. I liked how two turtle videos, especially the [Scope example](https://trinket.io/python/4b21944c2f), added basic code .py tabs you could import and how helper functions are used without throwing everything at us all at once 🙂. Seeing how helper functions work allowed me to understand its ability one at a time, giving me a chance to create something like this on my Clicky Turtle Starter:

```
# helper function for Tina to go up when clicked (clicky function):
def go_up(tina, x, y):
  """Tells a turtle to go somewhere with the pen up, then puts the pen down"""
  tina.penup()
  tina.goto(0,70)
  tina.pendown()


# when clicked, makes Tina go into the pond:
def clicky(x, y):
  go_up(tina, 0, -100)
  danny.penup()
  danny.goto(0,-100)
  danny.color("yellow")
  danny.write("Don't try to stop me! I like the water :(", None, "center", "12pt bold")
  ```
  
Here is the actual Trinket with a fun little twist I added on the [Clicky Turtle Starter](https://trinket.io/python/1be9239cce) :turtle: . Next time, I want to challenge myself by adding things such as: 
- How can I make Tina the turtle change color with every click?
- Can I change the color of Tina's trail when she moves with keys?
- Can I successfully make another ".py" tab on my own without any past material?

## Conclusion
I didn't really have a lightbulb moment, but I feel happy knowing that I am starting to think more like a coder. For the first time ever, **I am not panicking!** I still have some confusions wtih the setup function but I believe I can familiaze myself with it.

Thank you! 🧑‍🎨
  
