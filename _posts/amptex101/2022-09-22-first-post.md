---
layout: post
author: <amptex101>
title: "Allison P.'s First Post/Reflection!"
---

Hi! My name is Allison Pujol, but I usually go by AP. I am an English/Info Studies grad student. 
  I have some R background and am excited to learn more about Python! 

I have experienced a couple of lightbulb moments. Here is one of them: I realized that R and Python use a lot of the same commands and language. I learned about computers being very literal when I started learning how to use R and learning about Python and other coding software has really hammered in the idea that computers are the most literal things ever. 
Some confusion/some things I am still fuzzy about are how to import files into Python. Can you do that? Maybe that is advanced for where we are in the course. 
A problem solving strategy that has helped me is typing out code word for word, character by character, instead of copy pasting it. Here is some code from the class. 

```
def go_draw_circle(x, y, size):
    tina.penup()
    tina.goto(10,9)
    tina.circle(size)
    tina.pendown()
```
Here is another! 
```
def draw_square(self, custom_color = "green"):
    self.pendown()
    self.color(custom_color)
    self.fill(True)
    self.stamp()
    for i in range(4):
      self.forward(100)
      self.right(90)
      self.color("brown")
      self.stamp()
      self.color(custom_color)
    self.fill(False)
    self.color("brown")
    self.penup()
  
tina = BoxTurtle()

tina.goto(0,100)

tina.draw_square()

tina.left(45)
tina.goto(-100,-100)
tina.draw_square("pink")

tina.hideturtle()
```
