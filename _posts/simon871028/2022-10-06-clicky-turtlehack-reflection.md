---
layout: post
author: simon871028
title: "Feng's Clicky Turtlehack"
---

Here is my trinket code :

<iframe src="https://trinket.io/embed/python/fbf0c594fd" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

**Reflection**

I have been enjoying this course so far. 
Mr. Hauser has used a very interesting and interactive way to introduce us into the world of Python.
Although I've already got some experience in Python, I still get to learn something new such as using Trinket.
The Github tutorial and excercise is very helpful and useful as well.
Looking foward to learning new things in the following classes with Mr. Hauser.

For me, the hardest part of this assignment is to be creative. Thinking of a new graph pattern or think of a new way to display turtle is such a big work for me.
Eventually I modified the code a liite bit, allow the user to pick background color by :
```
color = input("Choose a background color :")
  screen.bgcolor(color)
```
Also, I make another function which can **clear** the past path for Tina the turtle :

```
def clear_path():
  tina.clear()

myscreen.onkey(clear_path,'space')
```
I still struggle with creating a helper function into my code, so I didn't implement it in this assignment. Hopefully I can work it out and try to add one or few into my code in the near future.
