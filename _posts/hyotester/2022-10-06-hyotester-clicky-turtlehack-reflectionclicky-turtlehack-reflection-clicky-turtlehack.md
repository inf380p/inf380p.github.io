---
layout: post
author: hyotester
title: "Hyo's Clicky Turtlehack"
---

Here is my trinket code :

<iframe src="https://trinket.io/embed/python/cf663b6257" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

**Reflection**
Hi, I'm hyojeong! I've already got promming experience in Python, but It's my first time to use Trinket to visualize. So, I'm really enjoying this coruse and thank professor since I'm leanring from you how to use Python to be interactive way to introduce us into the world of Python.
Looking foward to learning new things in the following classes!!

The hardest part of clicky's assignment is to control the turtle’s position and one other aspect of its state. Because I wanted to make the key like a pencil to write a message with interactive heart!! My topic is that "Send a letter to someone you love with your heart." But I'm not sure how to control the key to create curve. Please let me if you know that!!

# So, I just use keys

```
def go_left():
  tina.left(turn_amount)
  
def go_right():
  tina.right(turn_amount)
  
def go_forward():
  tina.forward(move_amount)
  
def go_backward():
  tina.backward(move_amount)
  
myscreen.onkey(go_left, 'left')
myscreen.onkey(go_right, 'right')
myscreen.onkey(go_forward, 'up')
myscreen.onkey(go_backward, 'down')

myscreen.listen()
```

# I also use Clicks

```
def clicky(x, y):
  tina.goto(x,y)

```


My experiment is to create interactive heart using 

# Math function 

I use math module since I had issues to use animation module. Here is a link to look at Math module: https://trinket.io/docs/python
```
def draw_heart(alpha,d):
  r = d/math.tan(math.radians(180-alpha/2))
  turtle.up()
  turtle.goto(0,-d*math.cos(math.radians(45)))
  turtle.seth(90-(alpha-180))
  turtle.down()
  turtle.begin_fill()
  turtle.fd(d)
  turtle.circle(r,alpha)
  turtle.left(180)
  turtle.circle(r,alpha)
  turtle.fd(d)
  turtle.end_fill()

a = 220
sign = -1
def animate():
  global a,sign
  turtle.clear()
  draw_heart(a,1000)
  screen.update()
  a += sign
  if a < 215:
    sign = -sign
  elif a > 220:
    sign = -sign
  screen.ontimer(animate,50)

animate()

```
