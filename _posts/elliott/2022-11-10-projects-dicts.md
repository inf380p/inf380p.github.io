---
author: elliott
category: notes
title: "Dictionaries & Intro to Classes"
layout: post
published: true
inprogress: false
mode: In Person
---
# Announcements

* We're beginning final projects today. Your first decision: Turtle or Text? This decision is entirely subjective: which is more engaging to you? You'll use the same language features of Python either way.
* I'm going to focus on introducing Class extension and helping you get an initial project plan today. *If you have Dictionaries questions that we don't get to today, save them*. We'll have plenty of time to review as you work on final projects the rest of the semester.
* Don't Panic.
* **Classhack assignment is now Extra Credit, and due next week**. Highly recommended for Turtlers, regular recommended for everyone else.

# Q&A

* Any questions or vocab?



# Extending the Turtle Class

Class **extension** is starting from a Class that's already defined and then setting it up in a custom way and/or teaching it how to do new things. Here's an example extension of the `Turtle` class:

```python
class BoxTurtle(turtle.Turtle):
  # Override some defaults:
  def __init__(self):
    # First, set up BoxTurtles like regular Turtles:
    turtle.Turtle.__init__(self)

    # Then, customize these things:
    self.speed(3)
    self.penup()
    self.shape("turtle")
    self.color("brown")

  # a custom method that makes `.draw_square` work on BoxTurtle objects
  def draw_square(self):
    for i in range(4):
      self.forward(100)
      self.right(90)
```

## Understanding `self`

Each instantiated object is different, and has different characteristics. These characteristics can be accessed via dot-notation on the `self` object.

When you're defining a class, `self` stands in for any particular object. Once you've created an object, you can think of it as if that were to be called on the object instead.

For instance, let's create a `BoxTurtle`:

```python
tina = BoxTurtle()
```

When this line of code runs, `__init__` tells Python how to set `tina` up. As part of that, this:

```python
    self.speed(3)
    self.penup()
    self.shape("turtle")
    self.color("brown")
```

...happens like this:
```python
    tina.speed(3)
    tina.penup()
    tina.shape("turtle")
    tina.color("brown")
```

And so on with other `BoxTurtles` we instantiate.

In fact, this has already been happening with  _all_ `Turtle` objects you've ever created! So, even though it might look unfamiliar, you're already familiar with its effects.

## Methods

Methods are things certain Classes of objects can do. With `Turtle` ojects, you can think of them as new skills you're teaching the Turtle.

Think _creating) methods like creating functions: you use the `def` keyword, except methods always get `self` as a parameter, and always have access to the particular object they're being called on.


Let's play!

<iframe src="https://trinket.io/embed/python/b777d5e932" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


# Selecting a Final Project Type: Turtle or Data Processing


We'll end the class today with a pull request containing your initial ideas. You'll revise these ideas in a _separate_ post due next week, and a draft of your program's interface.


# Final Project Guides.

Don't Panic!! These are references, intended to be helpful to you. Don't read them all for next week, but I would recommend reading the one that corresponds to your final project category, and the one on interfaces. Return to them as needed, and I'll also refer you to them if I think somehting will be useful to you.
