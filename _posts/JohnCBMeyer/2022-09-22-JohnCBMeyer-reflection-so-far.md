---
layout: post
author: JohnCBMeyer
title: "JohnCBMeyer's Embedded Trinket"
---

# What's a lightbulb that has gone on for you?
For some reason, I used to have trouble with functions in Python. No idea why.
They're similar enough to R that it feels like I shouldn't have had a problem,
but I never quite got it. In this class, one of the first things I did was write
a function to draw an arbitrarily-many-sided polygon. For some reason, it finally
just clicked.

Here's the polygon function:
```python
def draw_polygon(turtle, color, sides, size, x, y):
  turtle.penup()
  turtle.color("black")
  turtle.shape("turtle")
  turtle.fillcolor(color)
  turtle.goto(x,y)
  turtle.pendown()
  turtle.begin_fill()
  for i in range(sides):
    turtle.forward(size)
    turtle.left(360/sides)
  turtle.end_fill()
  turtle.setheading(0)
```

# Describe some confusion you've experienced.
I honestly hate Python documentation. R documentation always lists the args,
what they do, examples of acceptable input, and then has code samples below that
show how to get certain outputs. I've had a lot of trouble adjusting to Python's
documentation because everything is less clear and there's often no examples. I'm
starting to get more used to it, and I believe that will help me learn other languages
in the future, but it's definitely been work.

# What's still fuzzy for you? What will you do to make sure you can resolve your fuzziness?
So far, I think I understand most things pretty well, but I don't yet understand
scope in Python. For some reason, when I try to call a function inside a function
def statement, it doesn't work. I haven't yet figured out what I'm doing wrong,
but I'll be investigating StackOverflow and the docs to see.

The code I'm still having trouble with is below:

```python
def draw_random(turtle, rand, color = "black", lines = 10, line_length = 10):
  turtle.penup()
  turtle.color(color)
  turtle.shape("turtle")
  turtle.goto(0,0)
  turtle.pendown()
  for i in range(lines):
    turtle.forward(line_length)
    if rand % 2 == 0:
      turtle.right(rand)
    else:
      turtle.left(rand)
  turtle.setheading(0)
```

I tried to call the `randrange()` function within this def statement, but I
kept getting an error that said the function wasn't defined. I had already loaded
the package earlier in the script. I assume this was a problem of scope and the 
def statement doesn't have access to imported functions for some reason. So, I
tried defining a variable that calls `randrange()`, called `rand`, but
I'm having the same problem. I'll figure it out eventually, but I haven't sat down
and done so yet.

# What problem solving strategies have been working for you?
I've gotten pretty good at debugging over the last year or so. Any time I run into
an error, I always hunt down where the problem is, search online for similar problems,
look up the documentation if I'm using a packaged function, etc... Once I've done
all of that, I start tweaking things that I think might be wrong. If I try several
without any progress, sometimes I'll start from scratch (if the code isn't too long).
If it's an integral part of a larger script, I'll delete that block and rewrite it.
One thing I do a lot when I have problems with a complicated block is to start from
scratch and build several simple iterations leading up to what I want. So I'll start
with simple things like assignment and basic operations, make sure everything is
working, then move to conditionals and control structure. I'll keep adding on to
what I know works until something breaks, then I'll go back to hunting down why
whatever it is broke. So far, I haven't run into a problem that couldn't be solved
this way.

# My functional trinket
An iframe of my functional trinket can be found below.

<iframe src="https://trinket.io/embed/python/cdbbdec50e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
