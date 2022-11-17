---
layout: post
author: tommytestertwo
title: "Tommy Tester's First Focused Reflection"
---

This is my first post supercalajdfksjafd :) 

<iframe src="https://trinket.io/embed/python/da4b547add" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


___ 
## Reflection added Nov 17th
This is a reflection added much later. Imagine a few thoughtful paragraphs going here, using `inline code`, since later on in the semester I, tommytester, had a much better idea about what a good reflection looks like. Plus, my markdown skills have gotten better. 

This reflection should cover the assignment above and, optionally, meta-reflections about what I didn't understand at first about reflections, or about what I see now reading what I wrote back in September.

If I need to add new code, I'll do so with a *new* trinket. I'll then explain some of what I understand now, using syntax highlighted code blocks. 

Everything til now is just describing what reflections might be. Read on for a sample reflection from Tommy.

### Example reflection

In my first try at this assignment there were many things I didn't know about turtle. In revisiting this one, I wanted to see what these new skills might enable me to do.

The revised code below lets the user **drag** turtles, using the `.ondrag()` method. This method takes a function or method as **parameter**, and passes it the `x` and `y` coordinates of where the user drags. The `.onrelease()` method passes the `x` and `y` coordinates of where the user releases the button. If the pen is down, the turtle will draw. If it's up, the turtle will just move.

Using just these methods (and a little sleuthing), I was able to make a program sketch that allows the user to make a cake:

<iframe src="https://trinket.io/embed/pygame/097b14597e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

A tricky part here is that Python 3 turtle only uses `.begin_fill()`. When I instead was using `.fill(True)` and `.fill(False)`, the functions were failing, but not throwing an error. Compare these:

```python
  # orginal
  def top_layer(self, x, y):
    self.pendown()
    self.fill(True)
    self.forward(50)
    self.left(90)
    self.forward(20)
    self.left(90)
    self.forward(50)
    self.left(90)
    self.forward(20)
    self.fill(False)
    self.penup()
    self.hideturtle()
  
  # Fixed
  def top_layer(self, x, y):
    self.pendown()
    self.begin_fill()
    self.forward(50)
    self.left(90)
    self.forward(20)
    self.left(90)
    self.forward(50)
    self.left(90)
    self.forward(20)
    self.end_fill()
    self.penup()
    self.hideturtle()
```

This required closely reading the code, and noticing that the `.pendown()` was getting called, turning the turtles into drawing tools. The rest of the method wasn't happening. The error would sometimes pop up when I stopped the program, `Attribute Error: Turle object has no method .fill()`.

If I hadn't noticed this, I can now see another way of figuring it out. I would have needed to pull that code outside of the `.onrelease()` method, where the errors would show instantly:

<iframe src="https://trinket.io/embed/pygame/cabfe84229" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

The code above is an example of what I've seen called a _Minimum Working Example_ (MWE) on Stack Overflow. When someone's asking for help on something, those providing help ask for the minimal code that demonstrates the problem. In this case, my MWE would have helped me understand my error without needing Stack Overflow.

Error handling and flow of control get really complex when user events are added to the mix!

Overall, I learned the importance of reading closely, and am glad that I reflected on this. I saw an alternative problem solving strategy (making a MWE) that would have answered this question I had too, and that's likely to help me in the future when close reading of the code isn't enough.
